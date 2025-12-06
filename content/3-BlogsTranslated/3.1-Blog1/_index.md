---
title: "Blog 1"
date: "2025-09-22"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# Làm thế nào Zeta Global mở rộng việc thu thập dữ liệu đa khách hàng với Amazon S3 Tables

**bởi Soumil Shah, Varad Ram, Ananth Packkildurai, và Manoj Agarwal | ngày 22 tháng 9 năm 2025 | in Amazon Athena, Amazon EMR, Amazon S3 Tables, Amazon Simple Storage Service (S3), Customer Solutions, Intermediate (200) Permalink Comments Share**

Zeta Global là một công ty công nghệ tiếp thị dựa trên dữ liệu, sử dụng những hiểu biết về người tiêu dùng để giúp các thương hiệu trong việc thu hút, phát triển và giữ chân khách hàng. Trung tâm của hoạt động là Zeta Marketing Platform, một hệ thống tiên tiến ứng dụng trí tuệ nhân tạo (AI) và học máy (ML) trên dữ liệu độc quyền từ hơn 245 triệu hồ sơ người tiêu dùng tại Mỹ. Sự kết hợp mạnh mẽ này cho phép cung cấp những thông tin dự đoán và trải nghiệm cá nhân hóa quy mô lớn.

Zeta Global sử dụng Amazon S3 Tables — bảng quản lý Apache Iceberg — để vận hành nền tảng AI Marketing của mình. Kiến trúc của Zeta được xây dựng để xử lý quy mô lớn, quản lý hơn 10.000 bảng Iceberg, thu thập hàng trăm gigabyte dữ liệu mỗi ngày và xử lý 2 TB dữ liệu hàng ngày, đồng thời duy trì độ tươi mới của dữ liệu và tối ưu chi phí hiệu quả.

Bài viết này chia sẻ cách Zeta Global giải quyết các thách thức kinh doanh quan trọng: giảm thời gian tiếp cận thông tin từ dữ liệu tiếp thị streaming từ hàng giờ xuống còn vài phút, tối thiểu hóa chi phí tính toán trên từng khách hàng nhờ chia sẻ tài nguyên hiệu quả, và tối đa hóa giá trị của kiến trúc đa khách hàng (multi-tenant) để phục vụ hàng nghìn khách hàng cùng lúc. Giải pháp cần phải loại bỏ các silo dữ liệu làm chậm việc ra quyết định, giảm bớt gánh nặng vận hành khi quản lý các hệ thống rời rạc cho mỗi khách hàng, và đảm bảo dữ liệu luôn sẵn có đồng nhất cho tất cả khách hàng đồng thời mở rộng quy mô chi phí hợp lý khi số lượng khách hàng tăng lên.

---

## Thách thức

Trước khi triển khai giải pháp này, Zeta gặp một số thách thức quan trọng đang ảnh hưởng đến khả năng phục vụ khách hàng hiệu quả và giữ lợi nhuận cạnh tranh:

### Quy mô lớn và yêu cầu hạ tầng từ việc thực thi chiến dịch

Nền tảng tiếp thị của Zeta xử lý hàng trăm terabyte dữ liệu streaming mỗi ngày, do thực thi các chiến dịch thời gian thực trên hàng nghìn khách hàng. Mỗi chiến dịch tạo ra luồng dữ liệu liên tục về tương tác người tiêu dùng, tín hiệu hành vi, và chỉ số hiệu suất cần được thu thập ngay lập tức để tối ưu hóa chiến dịch kịp thời. Hạ tầng truyền thống không thể mở rộng hiệu quả theo chi phí để xử lý lượng dữ liệu khổng lồ này đồng thời duy trì khả năng truy cập dữ liệu dưới một phút, điều mà khách hàng Zeta kỳ vọng để điều chỉnh chiến dịch và đưa ra quyết định cá nhân hóa real-time.

### Tối ưu chi phí trên mỗi khách hàng trong môi trường đa khách hàng (multi-tenant)

Động lực chính cho việc hiện đại hóa nền tảng là giảm chi phí vận hành trên một khách hàng trong khi mở rộng quy mô kinh doanh của Zeta. Giải pháp trước đây yêu cầu tài nguyên hạ tầng riêng biệt cho mỗi khách hàng lớn, tạo ra sự lãng phí tài nguyên và khó đạt được hiệu quả quy mô lớn. Khi lượng khách hàng tăng từ vài trăm lên hàng nghìn, cấu trúc chi phí không thể duy trì, đe dọa khả năng giữ giá cạnh tranh trong khi vẫn đáp ứng hiệu suất cần thiết cho chiến dịch tiếp thị thành công.

### Yêu cầu độ tươi mới của dữ liệu cho quyết định tiếp thị real-time

Các chiến dịch tiếp thị cần truy cập tức thì tới dữ liệu mới nhất để tối ưu hóa chi tiêu quảng cáo, điều chỉnh các tham số mục tiêu và phản hồi nhanh sự thay đổi hành vi người tiêu dùng. Trễ dữ liệu làm mất cơ hội doanh thu và giảm hiệu quả chiến dịch. Kiến trúc cũ thường có độ trễ dữ liệu vài giờ trong các thời điểm tải cao, khiến khách hàng đưa ra quyết định dựa trên dữ liệu lỗi thời, có thể gây lãng phí ngân sách quảng cáo cho các chiến dịch kém hiệu quả.

---

## Kiến trúc giải pháp

Zeta sử dụng S3 Tables làm nền tảng cho hồ dữ liệu lakehouse, như thể hiện trong sơ đồ dưới đây. S3 Tables được thiết kế để tương thích với nhiều khung xử lý và công cụ truy vấn khác nhau, hỗ trợ cả pipeline xử lý hàng loạt (batch) và luồng dữ liệu (streaming).

{{< figure src="https://phucqb.sirv.com/Images/Zeta-Global-solution-architecture.png" title="Kiến trúc giải pháp Zeta Global" >}}

Kiến trúc gồm việc thu thập dữ liệu streaming từ Kafka vào một bucket Amazon S3 chung, với dữ liệu được phân vùng theo tenant ID. Bộ nhớ trung gian được dùng để lưu trữ dữ liệu thô và theo dõi các biến đổi. AWS Step Functions được dùng để lên lịch và điều phối các tác vụ chạy định kỳ. Phần tác vụ này kích hoạt các job Amazon EMR xử lý và ghi dữ liệu vào S3 Tables. Khi dữ liệu đã nằm trong S3 Tables, nó có thể được truy vấn bằng nhiều công cụ như Amazon Athena, EMR, và các ứng dụng bên thứ ba tương thích với Iceberg REST.

### Các thành phần chính trong kiến trúc của Zeta Global

- **AWS Step Functions là lớp điều phối** để khởi tạo và xử lý thu thập dữ liệu.

- **Phân vùng dữ liệu theo bucket cho xử lý song song** cho phép hệ thống xử lý đồng thời nhiều bộ dữ liệu của khách hàng khác nhau. Dữ liệu khách hàng được phân phối vào các "thùng" (bins) dựa trên hàm băm (hash function) và kích thước thùng định sẵn (ví dụ 2, 4, 8). Chiến lược phân vùng theo băm này cân bằng tải công việc trên các job, nâng cao hiệu năng hệ thống thông qua tính năng phân vùng ẩn của Apache Iceberg. Phân vùng ẩn này trừu tượng hóa bố cục vật lý dữ liệu để tối ưu hóa truy vấn và cho phép truy cập dữ liệu hiệu quả trên các tải công việc đa dạng, mà không làm phức tạp hóa việc phân vùng cho người dùng cuối.

- **Cơ chế khóa bi quan (pessimistic locking)** điều phối truy cập file trong bucket S3 chung và duy trì tính toàn vẹn dữ liệu, đảm bảo chỉ một job có thể xử lý file tại một thời điểm. Đội ngũ chọn khóa bi quan thay vì khóa lạc quan vì nó cam kết tính nhất quán mạnh và toàn vẹn dữ liệu, điều đặc biệt quan trọng với dữ liệu nhạy cảm tiếp thị. Mặc dù khóa bi quan có thể làm giảm hiệu năng do tranh chấp khóa có thể gây ra thời gian chờ lâu hoặc deadlock, rủi ro dữ liệu bị hỏng khi ghi cùng lúc lớn hơn nhiều so với nhược điểm này. Đảm bảo tính đúng đắn trong xử lý song song được ưu tiên hơn tối ưu băng thông thuần túy.

- **Các job Spark bất đồng bộ (Asynchronous Spark jobs)** được khởi chạy để xử lý từng bucket, kèm cơ chế hồi đáp (callback) để theo dõi tiến độ xử lý.

- **Cơ chế phục hồi lỗi tự động** quản lý khóa file bằng cách tự động giải phóng khóa trên các file xử lý thất bại sau nhiều lần thử không thành công. Nếu nhiều lần thử vẫn không thành công, luồng công việc được đánh dấu là thất bại.

---

## Điều phối luồng công việc

Zeta áp dụng mô hình "khóa trước, xử lý sau" (lock-first, process-later) tránh các điều kiện tranh chấp (race conditions) và trùng lặp ghi, như mô tả hình dưới đây.

{{< figure src="https://phucqb.sirv.com/Images/Step-Functions-workflow-orchestration.png" title="Điều phối luồng công việc" >}}

1. **Khóa được lấy:** Trước khi bắt đầu bất kỳ luồng thu thập dữ liệu nào, Step Functions sẽ lấy khóa.

2. **Phân vùng dữ liệu:** Sau khi khóa đã được giữ, hệ thống phân chia dữ liệu khách hàng vào các bucket theo hàm băm.

3. **Xử lý song song:** Các job Spark được khởi chạy bất đồng bộ để xử lý từng bucket, có kiểm soát độ đồng thời.

4. **Cơ chế hồi đáp:** Mỗi job Spark khi hoàn thành sẽ gửi callback cho Step Functions xác nhận thực thi thành công và cho phép giải phóng khóa.

5. **Xử lý lỗi:** Nếu có job thất bại, Step Functions sẽ dọn dẹp các khóa hoặc file tạm tồn đọng, giải phóng khóa, và đánh dấu luồng công việc là thất bại, hỗ trợ khả năng thử lại hiệu quả.

Step Functions cung cấp một điểm kiểm soát và quan sát duy nhất, làm bộ não điều phối trung tâm cho các luồng công việc đa khách hàng phức tạp. Điều này đặc biệt quan trọng với hệ thống đa khách hàng quản lý hàng nghìn bảng và khối lượng dữ liệu lớn, giúp đảm bảo áp dụng nhất quán logic nghiệp vụ như mô hình "khóa trước" cho tất cả khách hàng. Nền tảng đa khách hàng của Zeta đòi hỏi kiểm soát chặt chẽ và khả năng quan sát hệ thống, khiến một công cụ điều phối trung tâm như Step Functions là lựa chọn hợp lý so với kiến trúc phân tán cực độ, vốn thường được thấy ở các hệ thống phân tán quy mô lớn.

---

## Tối ưu hiệu năng và tinh chỉnh

Nền tảng thu thập dữ liệu của Zeta cung cấp nhiều tham số có thể cấu hình giúp nhà vận hành tùy chỉnh hiệu năng dựa trên yêu cầu khách hàng và giới hạn tài nguyên. 

- **Tham số kích thước bin** điều khiển phân phối dữ liệu khách hàng qua các bucket xử lý dựa trên thuật toán băm — ví dụ kích thước bin đặt thành 4 sẽ phân phối dữ liệu khách hàng trải qua 4 bucket riêng biệt, cho phép xử lý song song đồng thời duy trì tính địa phương dữ liệu và giảm thao tác ngang qua phân vùng.

- **Tham số độ đồng thời (concurrency)** quyết định số lượng job Spark tối đa có thể chạy cùng lúc trên tất cả các bucket, tạo một pipeline xử lý có kiểm soát, trong đó các job hoàn thành sẽ kích hoạt job tiếp theo từ hàng đợi bắt đầu xử lý ngay lập tức, đảm bảo sử dụng tài nguyên tối ưu mà không làm chật khối hệ thống.

- **Tham số số lượng thread workers** điều khiển độ song song bên trong từng job Spark riêng lẻ, cho phép kiểm soát tinh vi CPU và bộ nhớ trên mỗi thể unit xử lý.

Ba tham số tinh chỉnh này phối hợp cùng nhau mang đến khả năng kiểm soát chính xác sự cân bằng giữa hiệu năng và chi phí, cho phép hệ thống mở rộng từ xử lý bộ dữ liệu nhỏ của khách hàng với tài nguyên thấp đến xử lý workload quy mô doanh nghiệp với băng thông và khả năng xử lý song song tối đa.

Zeta Global đã dùng S3 Tables để đạt được khả năng mở rộng đặc biệt với hơn 4.000 bảng quản lý đa khách hàng, tính toàn vẹn dữ liệu với cam kết nhất quán khi xử lý song song, và hiệu quả vận hành xử lý hàng chục terabyte mỗi ngày với tối ưu tài nguyên. Nền tảng hỗ trợ linh hoạt với nhiều công cụ truy vấn đa dạng và khả năng phục hồi tự động qua cơ chế phục hồi lỗi. S3 Tables còn tăng cường các lợi ích này qua việc tối ưu file tự động, hợp nhất các đối tượng dữ liệu nhỏ thành các file lớn 512 MB giúp cải thiện hiệu năng truy vấn, quản lý snapshot tự động giữ và xóa các snapshot bảng theo thời gian, và xóa các file không còn dùng (orphaned files) để tối ưu lưu trữ.

---

## Kết luận

Việc triển khai nền tảng thu thập dữ liệu đa khách hàng mở rộng được xây dựng trên Amazon S3 Tables đã giúp Zeta Global quản lý và xử lý khối lượng dữ liệu khổng lồ một cách hiệu quả, trong khi đảm bảo tính toàn vẹn nghiêm ngặt của dữ liệu. Cách tiếp cận tham số hóa cho phép Zeta tối đa hóa băng thông xử lý và giảm chi phí để phù hợp với các mục tiêu mở rộng và hiệu năng phát triển.

Zeta Global sử dụng S3 Tables để tạo nên kiến trúc thu thập này, và nó chính là nền tảng của lakehouse dữ liệu mạnh mẽ, mở rộng và thực thi truy vấn hiệu quả của Zeta, hỗ trợ các yêu cầu ngày càng tăng của Marketing and Data Cloud platform.

**TAGS:** Amazon Athena, Amazon EMR, Amazon Simple Storage Service (Amazon S3)

---

## Tác giả

### Soumil Shah
Soumil Nitin Shah là kỹ sư cấp cao (Sr Software Engineer - Big Data) tại Zeta Global, chuyên xây dựng các giải pháp kỹ thuật dữ liệu có khả năng mở rộng. Anh thiết kế và triển khai các nền tảng đám mây bền vững biến dữ liệu phức tạp thành những hiểu biết có thể hành động được. Soumil tập trung phát triển các pipeline và hệ thống dữ liệu hiệu quả phù hợp mục tiêu chiến lược của Zeta Global. Tìm hiểu thêm về công việc của anh tại soumilshah.com.

### Varad Ram
Varad là kiến trúc sư giải pháp doanh nghiệp hỗ trợ mảng quảng cáo và tiếp thị tại AWS. Anh làm việc sát sao với người dùng để thiết kế các giải pháp có thể mở rộng và vận hành hiệu quả. Hiện tại, Varad tập trung chính vào phân tích và giúp người dùng tối đa hóa lợi tức đầu tư trong AI tạo nội dung (generative AI). Trong thời gian rảnh, Varad thích đạp xe cùng con và chơi tennis.

### Ananth Packkildurai
Ananth Packkildurai là kỹ sư chính tại Zeta, lãnh đạo kiến trúc nền tảng dữ liệu đa khách hàng mở rộng. Trước đây, anh từng giúp xây dựng nền tảng dữ liệu quy mô terabyte và cơ sở hạ tầng quan sát tại Slack. Với kinh nghiệm tại Bazaarvoice, Sephora và Evlov Inc., Ananth mang đến chuyên môn sâu sắc về kỹ thuật dữ liệu và hạ tầng. Anh cũng là tác giả của Data Engineering Weekly và cố vấn cho các startup dữ liệu giai đoạn đầu.

### Manoj Agarwal
Manoj Agarwal là kiến trúc sư chính tại Zeta Global, dẫn dắt thiết kế các nền tảng AI và dữ liệu quy mô lớn hỗ trợ giải pháp marketing và quảng cáo thời gian thực. Với hơn 25 năm kinh nghiệm tại Walmart, Salesforce và Amazon, Manoj chuyên về hệ thống phân tán, hạ tầng học máy và kiến trúc đám mây bản địa. Anh nắm giữ 13 bằng sáng chế và từng trình bày tại các hội thảo công nghệ hàng đầu. Tại Zeta, Manoj thúc đẩy việc áp dụng công nghệ lakehouse dữ liệu mở và tự động hóa dựa trên AI để cung cấp các giải pháp đa khách hàng mở rộng.

---
title: "Worklog Tuần 9"
date: "2025-11-03"
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---


### Mục tiêu tuần 9:

* Kết nối, làm quen với các thành viên trong First Cloud Journey.
* Hiểu dịch vụ AWS cơ bản, cách dùng console & CLI.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Learn about AWS Lambda basics: Function creation, handler, và permissions. <br> - **Thực hành:** Deploy first Lambda function sử dụng console và test invocation. | 03/11/2025   | 03/11/2025      | [AWS Lambda Docs](https://docs.aws.amazon.com/lambda/) |
| 3   | - Connect Lambda với **API Gateway** để expose RESTful endpoints. <br> - Test GET/POST requests sử dụng Postman. | 04/11/2025   | 04/11/2025      | [API Gateway Overview](https://docs.aws.amazon.com/apigateway/) |
| 4   | - Study **SNS** (Simple Notification Service). <br> - **Thực hành:** Create SNS topic và subscribe via email. | 05/11/2025   | 05/11/2025      | [AWS SNS Docs](https://docs.aws.amazon.com/sns/) |
| 5   | - Learn **SQS** (Simple Queue Service) cho message queuing. <br> - **Thực hành:** Send và receive messages sử dụng AWS Console và connect SQS to Lambda. | 06/11/2025   | 06/11/2025      | [AWS SQS Docs](https://docs.aws.amazon.com/sqs/) |
| 6   | - Explore **Step Functions** cho orchestrating workflows. <br> - **Thực hành:** Build a simple flow integrating Lambda, SQS, và SNS. <br> - Clean up serverless resources sau khi testing. | 07/11/2025   | 07/11/2025      | [AWS Step Functions Docs](https://docs.aws.amazon.com/step-functions/) |
| 7   | - **Serverless nâng cao:** EventBridge và DynamoDB integration <br> - Create event-driven architectures với EventBridge <br> - Implement Lambda functions với DynamoDB triggers | 08/11/2025   | 08/11/2025      | [AWS EventBridge Docs](https://docs.aws.amazon.com/eventbridge/) |
| 8   | - **Serverless Security:** IAM best practices cho Lambda <br> - Implement VPC endpoints cho serverless services <br> - Monitor và debug serverless applications | 09/11/2025   | 09/11/2025      | [AWS Serverless Security](https://cloudjourney.awsstudygroup.com/) |


### Kết quả đạt được tuần 9:

* Hiểu AWS là gì và nắm được các nhóm dịch vụ cơ bản: 
  * Compute
  * Storage
  * Networking 
  * Database
  * ...

* Đã tạo và cấu hình AWS Free Tier account thành công.

* Làm quen với AWS Management Console và biết cách tìm, truy cập, sử dụng dịch vụ từ giao diện web.

* Cài đặt và cấu hình AWS CLI trên máy tính bao gồm:
  * Access Key
  * Secret Key
  * Region mặc định
  * ...

* Sử dụng AWS CLI để thực hiện các thao tác cơ bản như:

  * Kiểm tra thông tin tài khoản & cấu hình
  * Lấy danh sách region
  * Xem dịch vụ EC2
  * Tạo và quản lý key pair
  * Kiểm tra thông tin dịch vụ đang chạy
  * ...

* Có khả năng kết nối giữa giao diện web và CLI để quản lý tài nguyên AWS song song.
* ...



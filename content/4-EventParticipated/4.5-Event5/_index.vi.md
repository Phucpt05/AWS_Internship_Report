---
title: "Event 5"
date: "2025-11-29"
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---



# Bài thu hoạch "AWS Cloud Mastery Series #3: Theo AWS Well-Architected Security Pillar"

### Mục Đích Của Sự Kiện

- Cung cấp kiến thức chuyên sâu về Security Pillar trong AWS Well-Architected Framework
- Hướng dẫn áp dụng các nguyên tắc bảo mật tốt nhất trên AWS
- Chia sẻ kinh nghiệm thực tế về bảo mật trong môi trường cloud tại Việt Nam
- Giới thiệu các công cụ và dịch vụ bảo mật trên AWS

### Thông Tin Sự Kiện

- **Thời gian:** 8:30 AM – 12:00 PM, Thứ Bảy, ngày 29/11/2025
- **Địa điểm:** Tầng 36, tòa nhà Bitexco, số 02 đường Hải Triều, phường Sài Gòn, thành phố Hồ Chí Minh

### Nội Dung Nổi Bật

#### 8:30 – 8:50 AM | Opening & Security Foundation
- Vai trò Security Pillar trong Well-Architected
- Nguyên tắc cốt lõi: Least Privilege – Zero Trust – Defense in Depth
- Shared Responsibility Model
- Top threats trong môi trường cloud tại Việt Nam

#### ⭐ Pillar 1 — Identity & Access Management
##### 8:50 – 9:30 AM | Modern IAM Architecture
- **IAM**: Users, Roles, Policies – tránh long-term credentials
- **IAM Identity Center**: SSO, permission sets
- **SCP & permission boundaries** cho multi-account
- **MFA**, credential rotation, Access Analyzer
- **Mini Demo**: Validate IAM Policy + simulate access

#### ⭐ Pillar 2 — Detection
##### 9:30 – 9:55 AM | Detection & Continuous Monitoring
- **CloudTrail** (org-level), GuardDuty, Security Hub
- Logging tại mọi tầng: VPC Flow Logs, ALB/S3 logs
- Alerting & automation với EventBridge
- Detection-as-Code (infrastructure + rules)

##### 9:55 – 10:10 AM | Coffee Break

#### ⭐ Pillar 3 — Infrastructure Protection
##### 10:10 – 10:40 AM | Network & Workload Security
- **VPC segmentation**, private vs public placement
- **Security Groups vs NACLs**: mô hình áp dụng
- **WAF + Shield + Network Firewall**
- Workload protection: EC2, ECS/EKS security basics

#### ⭐ Pillar 4 — Data Protection
##### 10:40 – 11:10 AM | Encryption, Keys & Secrets
- **KMS**: key policies, grants, rotation
- Encryption at-rest & in-transit: S3, EBS, RDS, DynamoDB
- **Secrets Manager & Parameter Store** — patterns rotation
- Data classification & access guardrails

#### ⭐ Pillar 5 — Incident Response
##### 11:10 – 11:40 AM | IR Playbook & Automation
- IR lifecycle theo AWS
- **Playbook**:
  - compromised IAM key
  - S3 public exposure
  - EC2 malware detection
  - Snapshot, isolation, evidence collection
- Auto-response bằng Lambda/Step Functions

##### 11:40 – 12:00 PM | Wrap-Up & Q&A
- Tổng kết 5 pillars
- Common pitfalls & thực tế doanh nghiệp Việt Nam
- Roadmap security learning (Security Specialty, SA Pro)

### Những Gì Học Được

#### Kiến thức nền tảng về Security Pillar
- Hiểu rõ 5 trụ cột bảo mật trong AWS Well-Architected Framework
- Nắm vững các nguyên tắc bảo mật cốt lõi: Least Privilege, Zero Trust, Defense in Depth
- Phân biệt rõ trách nhiệm giữa AWS và khách hàng theo Shared Responsibility Model

#### Kỹ năng thực hành
- Cấu trúc IAM hiện đại để tránh long-term credentials
- Thiết lập hệ thống detection và monitoring liên tục
- Áp dụng các lớp bảo mật cho network và workload
- Triển khai encryption cho data tại-rest và in-transit
- Xây dựng Incident Response playbook hiệu quả

#### Ứng dụng thực tế
- Nhận diện và xử lý các threats phổ biến tại Việt Nam
- Áp dụng Detection-as-Code cho infrastructure và rules
- Tự động hóa response với Lambda và Step Functions

### Trải nghiệm trong event

Tham gia workshop **"AWS Cloud Mastery Series #3: Theo AWS Well-Architected Security Pillar"** đã mang lại cho tôi kiến thức chuyên sâu về bảo mật trên AWS:

#### Học hỏi từ chuyên gia
- Các chuyên gia AWS đã chia sẻ kiến thức chuyên sâu về 5 trụ cột bảo mật
- Được hướng dẫn trực tiếp cách áp dụng các best practices của Security Pillar
- Hiểu rõ hơn về các threats đặc thù trong môi trường cloud tại Việt Nam

#### Trải nghiệm thực hành
- Trực tiếp thực hành validate IAM Policy và simulate access
- Thử nghiệm với các công cụ detection như CloudTrail, GuardDuty, Security Hub
- Áp dụng các kỹ thuật bảo mật cho VPC, Security Groups, NACLs
- Triển khai encryption với KMS cho các dịch vụ AWS khác nhau

#### Kết nối và chia sẻ
- Gặp gỡ và trao đổi với các chuyên gia bảo mật khác trong ngành
- Học hỏi từ các case study thực tế về incident response
- Mở rộng mạng lưới kết nối trong cộng đồng security tại Việt Nam

#### Bài học rút ra
- Bảo mật là trách nhiệm chung (Shared Responsibility) và cần được xem xét ngay từ đầu
- Việc áp dụng nguyên tắc Least Privilege giúp giảm đáng kể rủi ro bảo mật
- Detection và monitoring liên tục là yếu tố quan trọng để phát hiện sớm các threats
- Incident Response playbook cần được xây dựng và thử nghiệm thường xuyên
- Automation là chìa khóa để response nhanh và hiệu quả khi có sự cố

> Workshop này đã trang bị cho tôi kiến thức và kỹ năng cần thiết để thiết kế và triển khai các giải pháp bảo mật tuân thủ AWS Well-Architected Security Pillar, đồng thời cung cấp lộ trình rõ ràng để phát triển chuyên môn trong lĩnh vực bảo mật trên AWS.
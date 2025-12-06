---
title: "Event 5"
date: "2025-11-29"
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---



# Workshop Report "AWS Cloud Mastery Series #3: AWS Well-Architected Security Pillar"

### Event Purpose

- Provide in-depth knowledge about the Security Pillar in AWS Well-Architected Framework
- Guide application of security best practices on AWS
- Share practical experience about security in cloud environments in Vietnam
- Introduce security tools and services on AWS

### Event Information

- **Time:** 8:30 AM – 12:00 PM, Saturday, November 29, 2025
- **Location:** 36th Floor, Bitexco Tower, 02 Hai Trieu Street, Saigon Ward, Ho Chi Minh City

### Key Content

#### 8:30 – 8:50 AM | Opening & Security Foundation
- Role of Security Pillar in Well-Architected
- Core principles: Least Privilege – Zero Trust – Defense in Depth
- Shared Responsibility Model
- Top threats in cloud environments in Vietnam

#### ⭐ Pillar 1 — Identity & Access Management
##### 8:50 – 9:30 AM | Modern IAM Architecture
- **IAM**: Users, Roles, Policies – avoiding long-term credentials
- **IAM Identity Center**: SSO, permission sets
- **SCP & permission boundaries** for multi-account
- **MFA**, credential rotation, Access Analyzer
- **Mini Demo**: Validate IAM Policy + simulate access

#### ⭐ Pillar 2 — Detection
##### 9:30 – 9:55 AM | Detection & Continuous Monitoring
- **CloudTrail** (org-level), GuardDuty, Security Hub
- Logging at all layers: VPC Flow Logs, ALB/S3 logs
- Alerting & automation with EventBridge
- Detection-as-Code (infrastructure + rules)

##### 9:55 – 10:10 AM | Coffee Break

#### ⭐ Pillar 3 — Infrastructure Protection
##### 10:10 – 10:40 AM | Network & Workload Security
- **VPC segmentation**, private vs public placement
- **Security Groups vs NACLs**: application model
- **WAF + Shield + Network Firewall**
- Workload protection: EC2, ECS/EKS security basics

#### ⭐ Pillar 4 — Data Protection
##### 10:40 – 11:10 AM | Encryption, Keys & Secrets
- **KMS**: key policies, grants, rotation
- Encryption at-rest & in-transit: S3, EBS, RDS, DynamoDB
- **Secrets Manager & Parameter Store** — rotation patterns
- Data classification & access guardrails

#### ⭐ Pillar 5 — Incident Response
##### 11:10 – 11:40 AM | IR Playbook & Automation
- IR lifecycle according to AWS
- **Playbook**:
  - compromised IAM key
  - S3 public exposure
  - EC2 malware detection
  - Snapshot, isolation, evidence collection
- Auto-response with Lambda/Step Functions

##### 11:40 – 12:00 PM | Wrap-Up & Q&A
- Summary of 5 pillars
- Common pitfalls & Vietnamese enterprise realities
- Security learning roadmap (Security Specialty, SA Pro)

### Key Learnings

#### Security Pillar Fundamentals
- Understanding the 5 security pillars in AWS Well-Architected Framework
- Mastering core security principles: Least Privilege, Zero Trust, Defense in Depth
- Clearly distinguishing responsibilities between AWS and customers according to Shared Responsibility Model

#### Practical Skills
- Building modern IAM architecture to avoid long-term credentials
- Setting up continuous detection and monitoring systems
- Applying security layers for network and workloads
- Implementing encryption for data at-rest and in-transit
- Building effective Incident Response playbooks

#### Real-world Applications
- Identifying and handling common threats in Vietnam
- Applying Detection-as-Code for infrastructure and rules
- Automating response with Lambda and Step Functions

### Event Experience

Participating in the **"AWS Cloud Mastery Series #3: AWS Well-Architected Security Pillar"** workshop provided me with in-depth knowledge about security on AWS:

#### Learning from Experts
- AWS experts shared in-depth knowledge about the 5 security pillars
- Direct guidance on applying Security Pillar best practices
- Better understanding of specific threats in cloud environments in Vietnam

#### Hands-on Experience
- Direct practice validating IAM Policies and simulating access
- Experimenting with detection tools like CloudTrail, GuardDuty, Security Hub
- Applying security techniques for VPC, Security Groups, NACLs
- Implementing encryption with KMS for different AWS services

#### Networking and Sharing
- Meeting and exchanging with other security professionals in the industry
- Learning from real case studies about incident response
- Expanding professional network in the Vietnamese security community

#### Key Takeaways
- Security is a shared responsibility and needs to be considered from the beginning
- Applying the Least Privilege principle significantly reduces security risks
- Continuous detection and monitoring are essential for early threat detection
- Incident Response playbooks need to be built and tested regularly
- Automation is key to fast and effective response when incidents occur

> This workshop equipped me with the necessary knowledge and skills to design and implement security solutions that comply with AWS Well-Architected Security Pillar, while also providing a clear roadmap for professional development in the security field on AWS.
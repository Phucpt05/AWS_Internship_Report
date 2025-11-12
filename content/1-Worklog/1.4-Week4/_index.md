---
title: "Week 4 Worklog"
date: "2025-09-09"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Week 4 Objectives:

* Connect with First Cloud Journey (FCJ) team members and understand internship guidelines.
* Master AWS service categories: Compute, Storage, Networking, and Database fundamentals.
* Deep-dive into AWS Storage services with hands-on practice.
* Develop proficiency in AWS Console and CLI for storage resource management.



### Weekly Task Schedule:
| Day | Tasks | Start Date | Completion Date | Resources |
|-----|-------|------------|----------------|-----------|
| 2 | - FCJ team orientation<br>- Review internship policies and procedures | 06/12/2025 | 06/12/2025 | Internal documentation |
| 3 | - Study AWS service architecture and categorization<br>- Focus on Compute, Storage, Networking, Database services | 07/12/2025 | 07/12/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 4 | - AWS Free Tier account setup<br>- AWS CLI installation and configuration<br>- Practice basic CLI commands | 08/12/2025 | 08/12/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 5 | - Comprehensive AWS Storage services study:<br>&emsp;• Amazon S3 (buckets, storage classes, access points)<br>&emsp;• Amazon Glacier archival storage<br>&emsp;• Snow Family data migration<br>&emsp;• Storage Gateway hybrid solutions<br>&emsp;• AWS Backup centralized backup | 09/12/2025 | 09/12/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 6 | - Hands-on Labs: S3 bucket creation and configuration<br>- Infrastructure deployment and backup plan implementation<br>- VM Import/Export testing<br>- Access Control Lists (ACL) configuration | 10/12/2025 | 10/12/2025 | <https://cloudjourney.awsstudygroup.com/> |
| 7 | - Advanced Labs: Storage Gateway file share setup<br>- FSx Multi-AZ testing (performance, deduplication, quotas)<br>- CloudFront CDN integration<br>- Storage scaling and monitoring | 11/12/2025 | 11/12/2025 | <https://cloudjourney.awsstudygroup.com/> |

---

### Week 4 Key Achievements:

### AWS Service Architecture Mastery
* Gained comprehensive understanding of AWS service categories and their interconnections.
* Learned the distinction between object storage (S3) and block storage (EBS) architectures.
* Understood the "Write Once, Read Many" (WORM) principle for object storage optimization.

### Amazon S3 Deep Dive
* **Core Concepts**: Object-level storage with HTTP/HTTPS API access, bucket creation and management.
* **Storage Classes**: Mastered cost optimization through S3 Standard, Standard-IA, Intelligent-Tiering, One Zone-IA, and Glacier archive classes.
* **Access Points**: Learned to create multiple application-specific endpoints for single S3 buckets with granular permission control.
* **Lifecycle Management**: Configured automated object transitions between storage classes based on access patterns.
* **Advanced Features**: Implemented versioning, cross-region replication, and static website hosting.

### Storage Gateway & Hybrid Solutions
* Set up Storage Gateway for seamless on-premises to AWS integration.
* Tested file share mounting and hybrid cloud storage workflows.
* Practiced VM export/import using AWS VM Import/Export service.

### FSx File Systems
* Created and configured Multi-AZ FSx file systems (both SSD and HDD).
* Tested advanced features: data deduplication, shadow copies, user quotas.
* Performed throughput and storage capacity scaling exercises.
* Monitored performance metrics and optimized configurations.

### Backup & Recovery
* Implemented AWS Backup centralized backup strategies.
* Tested backup and restore procedures across multiple AWS services.
* Configured backup notifications and monitoring.

### Practical Skills Developed
* Proficient in both AWS Console GUI and CLI operations for storage management.
* Ability to design cost-effective storage architectures using appropriate storage classes.
* Experience with disaster recovery planning using AWS storage services.
* Understanding of performance optimization for different storage workloads.

---

### Technical Highlights

**S3 Object Lifecycle Automation**: Successfully implemented automatic transitions from S3 Standard → Standard-IA (30 days) → Glacier (60 days) → Deep Archive (90 days).

**Multi-Region Replication**: Configured cross-region replication for disaster recovery scenarios.

**CloudFront Integration**: Enhanced static website performance by implementing CloudFront CDN with S3 origin.

**Storage Cost Optimization**: Learned to balance storage costs vs. request costs across different S3 storage classes.

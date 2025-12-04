---
title: "Week 7 Worklog"
date: "2025-10-20"
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:
* Reinforce understanding of AWS core database services through hands-on repetition.
* Review key concepts from previous weeks: EC2, VPC, RDS, Aurora, Redshift, and ElastiCache.
* Develop practical confidence in deploying, connecting, and managing AWS resources.
* Focus on error handling, automation, and cost optimization in database workflows.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                  | Start Date | Completion Date | Reference Material                        |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ----------------------------------------- |
| 1   | - Review AWS database fundamentals <br>&emsp; + RDS instance lifecycle <br>&emsp; + Backup & Restore <br>&emsp; + Security Groups & IAM roles                                                        | 20/10/2025 | 20/10/2025      | AWS Study Group Labs Week 6               |
| 2   | - Recreate VPC, EC2, and RDS setup from scratch <br>&emsp; + Test connectivity between instances <br>&emsp; + Verify subnet and routing configurations                                                | 21/10/2025 | 21/10/2025      | Lab 05 Review                             |
| 3   | - Practice deploying Aurora cluster and performing migrations <br>&emsp; + MSSQL → Aurora MySQL <br>&emsp; + Oracle → MySQL schema conversion                                                        | 22/10/2025 | 22/10/2025      | Lab 43 Review                             |
| 4   | - Automate deployment using AWS CLI <br>&emsp; + Create and delete instances via command line <br>&emsp; + Configure DB parameters using CLI commands                                                 | 23/10/2025 | 23/10/2025      | AWS CLI Documentation                     |
| 5   | - Troubleshoot simulated issues <br>&emsp; + Memory pressure test <br>&emsp; + Table constraint errors <br>&emsp; + Network timeout resolution                                                        | 24/10/2025 | 24/10/2025      | Lab 43 (Modules 244–245)                  |
| 6   | - Recap session and prepare weekly summary report <br>&emsp; + Reflect on challenges and fixes <br>&emsp; + Plan next modules (e.g., serverless databases, DynamoDB)                                 | 25/10/2025 | 25/10/2025      | AWS Study Group Summary                   |
| 7   | - **Advanced Practice:** Performance optimization and monitoring <br>&emsp; + Database benchmarking <br>&emsp; + Query performance analysis <br>&emsp; + Cost optimization strategies | 26/10/2025 | 26/10/2025      | AWS Study Group Advanced                  |

### Week 7 Achievements:
* Consolidated all concepts learned in previous weeks through multiple rebuild and test cycles.
* Repeatedly deployed **VPC + EC2 + RDS** environment until stable connection was achieved.
* Improved confidence in **AWS CLI automation**:
  * Created RDS instances via command line.
  * Listed databases, regions, and subnets using CLI queries.
  * Managed security groups and parameter groups programmatically.
* Successfully completed multiple **migration simulations** (MSSQL → Aurora MySQL, Oracle → MySQL).
* Practiced troubleshooting complex issues including:
  * Memory pressure and slow query optimization.
  * Constraint and connectivity errors.
  * Backup and restore failures.
* Developed deeper understanding of cost efficiency, monitoring, and cleanup best practices.
* Ready to advance to **serverless and NoSQL database concepts (DynamoDB, Athena)** in the following week.

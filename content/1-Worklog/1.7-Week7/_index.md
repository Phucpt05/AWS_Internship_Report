---
title: "Week 7 Worklog"
date: "2025-10-04"
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 7 Objectives:
* Reinforce understanding of AWS core database services through hands-on repetition.
* Review key concepts from previous weeks: EC2, VPC, RDS, Aurora, Redshift, and ElastiCache.
* Develop practical confidence in deploying, connecting, and managing AWS resources.
* Focus on error handling, automation, and cost optimization in database workflows.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                  | Start Date | Completion Date | Reference Material                        |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ----------------------------------------- |
| 1   | - Review AWS database fundamentals <br>&emsp; + RDS instance lifecycle <br>&emsp; + Backup & Restore <br>&emsp; + Security Groups & IAM roles                                                        | 09/29/2025 | 09/29/2025      | AWS Study Group Labs Week 6               |
| 2   | - Recreate VPC, EC2, and RDS setup from scratch <br>&emsp; + Test connectivity between instances <br>&emsp; + Verify subnet and routing configurations                                                | 09/30/2025 | 09/30/2025      | Lab 05 Review                             |
| 3   | - Practice deploying Aurora cluster and performing migrations <br>&emsp; + MSSQL → Aurora MySQL <br>&emsp; + Oracle → MySQL schema conversion                                                        | 10/01/2025 | 10/01/2025      | Lab 43 Review                             |
| 4   | - Automate deployment using AWS CLI <br>&emsp; + Create and delete instances via command line <br>&emsp; + Configure DB parameters using CLI commands                                                 | 10/02/2025 | 10/02/2025      | AWS CLI Documentation                     |
| 5   | - Troubleshoot simulated issues <br>&emsp; + Memory pressure test <br>&emsp; + Table constraint errors <br>&emsp; + Network timeout resolution                                                        | 10/03/2025 | 10/03/2025      | Lab 43 (Modules 244–245)                  |
| 6   | - Recap session and prepare weekly summary report <br>&emsp; + Reflect on challenges and fixes <br>&emsp; + Plan next modules (e.g., serverless databases, DynamoDB)                                 | 10/04/2025 | 10/04/2025      | AWS Study Group Summary                   |

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

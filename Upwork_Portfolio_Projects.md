# Upwork Portfolio Project Drafts

This file turns the AWS projects in this workspace into portfolio-ready entries for Upwork.
Each entry is structured around the fields used in the portfolio form: project title, your role, project description, skills and deliverables, and suggested content.

## 1. Dynamic Cafe Website on AWS EC2

**Project title:** Dynamic Cafe Website Deployment on AWS EC2

**Your role:** AWS Cloud Engineer

**Project description:**
Built and deployed a dynamic cafe website on Amazon EC2 using a LAMP stack. Configured Apache, PHP, and MariaDB, integrated AWS Secrets Manager for secure credential handling, loaded the application database, and validated the customer ordering flow. Created an AMI to support replication into another AWS Region and confirmed the application worked as expected in a production-style setup.

**Skills and deliverables:**
Amazon EC2, LAMP stack, PHP, MariaDB, AWS Secrets Manager, AMI creation, multi-Region deployment, web application hosting.

**Suggested content:**
Use screenshots of the EC2 setup, the application running in the browser, the database settings form, and the final multi-Region deployment result.

## 2. Cafe Database Migration to Amazon RDS

**Project title:** Cafe Database Migration to Amazon RDS

**Your role:** Database Engineer

**Project description:**
Migrated a MariaDB database from an EC2 instance to Amazon RDS. Exported the existing schema and data with mysqldump, created and secured an RDS instance, imported the data, and reconfigured the cafe application to use the managed database. Verified that order history, CRUD operations, and persistent application data all worked correctly after the move.

**Skills and deliverables:**
Amazon RDS, MariaDB, mysqldump, database migration, AWS Security Groups, AWS Secrets Manager, application reconfiguration, data validation.

**Suggested content:**
Add screenshots of the RDS configuration, the migration steps, the application settings page, and the database-connected result.

## 3. Secure VPC Networking for a Cafe Application

**Project title:** Secure VPC Networking for a Cafe Application

**Your role:** AWS Network Engineer

**Project description:**
Designed a secure VPC networking environment for a cafe application with public and private subnets, an internet gateway, a bastion host, a NAT gateway, and network ACLs. Built the routing and access controls needed to support secure administrative access and private application hosting while keeping internal resources isolated from direct internet exposure.

**Skills and deliverables:**
Amazon VPC, subnet design, CIDR planning, internet gateway, NAT gateway, bastion host, network ACLs, security groups, SSH access.

**Suggested content:**
Use the VPC architecture screenshots, subnet and route table views, bastion host setup, and connectivity verification images.

## 4. Amazon RDS MySQL Setup and Application Integration

**Project title:** Amazon RDS MySQL Setup and Application Integration

**Your role:** Database / Cloud Engineer

**Project description:**
Created an Amazon RDS MySQL database in a free-tier configuration and connected it to a web application. Configured compute, storage, and network settings, retrieved the database endpoint, stored credentials securely in AWS Secrets Manager, and validated that the application could read and write data reliably across sessions.

**Skills and deliverables:**
Amazon RDS, MySQL, AWS Secrets Manager, EC2 integration, database configuration, storage planning, network security, data persistence.

**Suggested content:**
Add the RDS creation pages, the application settings screen, the Secrets Manager secret view, and the working application after connection.

## 5. Amazon VPC Design with Public and Private Subnets

**Project title:** Amazon VPC Design with Public and Private Subnets

**Your role:** AWS Network Engineer

**Project description:**
Built a VPC from the ground up with CIDR planning, public and private subnets, route tables, and an internet gateway. Deployed an application server in the public subnet, configured access controls, and validated end-to-end connectivity. This project demonstrates the core design patterns used to separate internet-facing and private resources in AWS.

**Skills and deliverables:**
Amazon VPC, CIDR planning, public subnet, private subnet, route tables, internet gateway, security groups, EC2 deployment.

**Suggested content:**
Use screenshots of the VPC creation, subnet layout, route table configuration, and final server validation.

## 6. VPC Peering and Flow Log Monitoring for Private Connectivity

**Project title:** VPC Peering and Flow Log Monitoring for Private Connectivity

**Your role:** AWS Network Engineer

**Project description:**
Created a VPC peering connection between an application VPC and a shared database VPC, then configured route tables in both directions so traffic could flow privately. Enabled VPC Flow Logs in CloudWatch, tested application-to-database connectivity, and analyzed the captured traffic to confirm that MySQL communication was routed correctly through the peering connection.

**Skills and deliverables:**
VPC peering, route table configuration, CloudWatch Logs, VPC Flow Logs, private connectivity, traffic analysis, MySQL networking, multi-VPC architecture.

**Suggested content:**
Add the peering connection status, the route table entries, the CloudWatch log streams, and the final application connection result.

## 7. Amazon EFS Shared File System Setup and Performance Testing

**Project title:** Amazon EFS Shared File System Setup and Performance Testing

**Your role:** Cloud Infrastructure Engineer

**Project description:**
Provisioned an Amazon EFS file system, configured security groups for NFS access, mounted the file system to an EC2 instance, and benchmarked performance with fio. Monitored throughput in CloudWatch to confirm shared file storage behavior and validate the scaling characteristics of EFS in a real AWS environment.

**Skills and deliverables:**
Amazon EFS, EC2, NFS, security groups, Linux administration, fio benchmarking, CloudWatch metrics, file storage architecture.

**Suggested content:**
Use screenshots of the EFS creation page, the mount command output, the fio test results, and the CloudWatch throughput graphs.

## Suggested Order For Upwork

If you want to publish these portfolio items in a clean sequence, I recommend this order:

1. Amazon VPC Design with Public and Private Subnets
2. Secure VPC Networking for a Cafe Application
3. VPC Peering and Flow Log Monitoring for Private Connectivity
4. Amazon RDS MySQL Setup and Application Integration
5. Cafe Database Migration to Amazon RDS
6. Dynamic Cafe Website on AWS EC2
7. Amazon EFS Shared File System Setup and Performance Testing

This order moves from foundational networking to database and application work, then finishes with storage and performance testing.
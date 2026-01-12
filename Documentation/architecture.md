
## Overview
This project implements a highly available and scalable web application on AWS using an EC2-based architecture.  
The design follows AWS Well-Architected Framework principles with a focus on reliability, security, performance efficiency, and cost optimization.

## Architecture Components

### 1. Virtual Private Cloud (VPC)
- Custom VPC with CIDR block `10.0.0.0/16` across two Availability Zones for high availability

### 2. Subnets
- **Public Subnets**
  - Deployed in two Availability Zones
  - Host the Application Load Balancer and the internet-facing web EC2 instances

- **Database Subnets (Optional)**
  - Used for Amazon RDS Multi-AZ deployment


### 3. Application Load Balancer (ALB)
- Distributes incoming HTTP traffic across EC2 instances
- Deployed in public subnets
- Performs health checks on EC2 instances
- Improves availability and fault tolerance


### 4. Auto Scaling Group (ASG)
- Automatically adjusts the number of EC2 instances based on demand
- Spans multiple Availability Zones
- Uses a Launch Template with user data to install and configure the web server


### 5. Compute Layer (EC2)
- EC2 instances deployed in public subnets
- No public IP addresses assigned
- Accesses the internet via ALB only
- Uses IAM Role for AWS service access

### 6. Database Layer (Optional)
- Amazon RDS (MySQL or PostgreSQL)
- Multi-AZ deployment for high availability
- Deployed in private subnets
- Automated backups enabled

## Architecture Flow
1. User sends HTTP request
2. Request reaches the Application Load Balancer
3. ALB forwards traffic to healthy EC2 instances
4. EC2 instances serve the web application
5. (Optional) EC2 connects securely to RDS


## High Availability Design
- Multi-AZ deployment
- Load balancing across instances
- Auto healing through ASG health checks

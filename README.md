# AWS-Scalable-Web-Application
This project demonstrates the design and deployment of a highly available and scalable web application on AWS using EC2, Application Load Balancer (ALB), and Auto Scaling Group (ASG).   The architecture follows AWS best practices for security, scalability, and cost optimization.

---

## Solution Architecture


### Architecture Flow
User → Application Load Balancer → EC2 Auto Scaling Group → (Optional) RDS Multi-AZ


## AWS Services Used
- Amazon EC2
- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- Amazon VPC
- IAM Roles
- Amazon CloudWatch
- Amazon SNS
- (Optional) Amazon RDS (Multi-AZ)


## Network Design
- Custom VPC (10.0.0.0/16)
- Two Availability Zones
- Public Subnets for ALB and EC2 instances
- Internet Gateway for inbound traffic

## Security Best Practices
- Security Groups with least privilege access
- IAM Role attached to EC2 (no hardcoded credentials)
- RDS deployed in private subnets (Optional)
- ALB handles public traffic only

## Scalability & High Availability
- Auto Scaling Group spans multiple Availability Zones
- Scaling policies based on CPU utilization
- ALB distributes traffic evenly across healthy instances
- Health checks ensure fault tolerance

## Cost Optimization
- Auto Scaling reduces costs during low traffic
- Use of burstable EC2 instances (t3.micro)
- No idle resources
- Pay-as-you-go model

## Deployment Steps
1. Create VPC, subnets, and networking components
2. Configure Security Groups
3. Create IAM Role for EC2
4. Create Launch Template with User Data
5. Configure Auto Scaling Group
6. Create Application Load Balancer
7. Configure CloudWatch alarms and SNS notifications

## Monitoring & Logging
- CloudWatch metrics for EC2 and ALB
- CloudWatch Alarms for scaling actions
- SNS notifications for alerts

## Testing
- Verify application access via ALB DNS
- Simulate load to test Auto Scaling behavior
- Monitor instance health and scaling events

## 📎 Screenshots
Screenshots of ALB, ASG, and CloudWatch metrics are available in the `screenshots/` folder.

## Author
**AbdElrahman Fawaz**  

## Security Principles
The project follows the principle of least privilege to ensure secure access to AWS resources.

## Network Security

### Security Groups
- **ALB Security Group**
  - Allows inbound HTTP (Port 80) from `0.0.0.0/0`
- **EC2 Security Group**
  - Allows inbound HTTP only from ALB Security Group

## IAM Security

### IAM Roles
- EC2 instances use IAM Roles instead of access keys
- Role permissions include:
  - CloudWatch logging
  - SNS publishing

## Data Security (Optional)
- RDS deployed in private subnets
- Database not publicly accessible
- Encrypted storage enabled (Optional)

## Monitoring & Auditing
- CloudWatch logs enabled
- CloudWatch alarms configured
- SNS notifications for operational alert

## Best Practices Applied
- No hardcoded credentials
- Private subnets for compute and database
- Controlled inbound and outbound traffic
- AWS-managed services used wherever possible

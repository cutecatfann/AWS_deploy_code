# Highly Available Web App - AWS CloudFormation Template

## Overview
This AWS CloudFormation template provisions a highly available web application infrastructure spanning two availability zones. It includes EC2 instances, an Auto Scaling group, a load balancer, and an RDS database with a read replica for fault tolerance and scalability.

## Features
- Networking: VPC with public and private subnets across two availability zones.
- Compute: EC2 instances deployed in public subnets.
- Scaling: Auto Scaling group with scaling policies based on CPU utilization.
- Load Balancer: Application Load Balancer (ALB) for traffic distribution.
- Database:*RDS MySQL instance with a read replica in a separate availability zone.
- Security: Security groups to control traffic flow.

## Usage
### Prerequisites
1. AWS CLI and CloudFormation configured.
2. Replace placeholders in the template with your values:
   - `ImageId` (AMI ID for EC2 instances)
   - `KeyName` (key pair for SSH access)
   - `MasterUserPassword` (secure RDS password).

### Deployment Steps
1. Upload the template to your AWS environment.
2. Execute the following command:
   ```bash
   aws cloudformation create-stack --stack-name HAWAStack --template-body file://template.yaml --capabilities CAPABILITY_NAMED_IAM
   ```
3. Monitor the stack creation process in the AWS Management Console.

### Outputs
- Web App accessible via the ALB URL.
- RDS database accessible within the private subnet.

## Notes
- Replace placeholders before deployment.
- Ensure IAM roles and permissions are configured properly.
- Modify security groups for custom rules if required.

## Cleanup
To delete the stack:
```bash
aws cloudformation delete-stack --stack-name HAWAStack
```

## License
This template is provided as-is without warranties. Use at your own risk :)


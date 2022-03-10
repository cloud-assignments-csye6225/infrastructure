# infrastructure

This repo contains the AWS Cloudformation template to deploy a VPC with 3 subnets, public route table and an Internet Gateway using YAML

- Added ec2 instance and application security groups resources to cloudformation template

Iaac build Instructions:
1. Set the profile and region environment variables through aws cli
   - export AWS_PROFILE=prod
   - export AWS_REGION=us-east-1
2. Use the aws cli and run aws create-stack command to run the infrastructure deployment
   
   aws cloudformation create-stack --stack-name a3 --template-body file://csye6225-infra.yml --parameters ParameterKey=vpcCIDR,ParameterValue="10.0.0.0/16" ParameterKey=aSubnetCIDR,ParameterValue="10.0.1.0/24" ParameterKey=bSubnetCIDR,ParameterValue="10.0.2.0/24" ParameterKey=cSubnetCIDR,ParameterValue="10.0.3.0/24" ParameterKey=imageId,ParameterValue="ami-01bb6863d65274c90" --capabilities CAPABILITY_NAMED_IAM

3. Verify if the stack and the aws resources are reflecting with given configuration on the aws console

- Added additional private subnets, DB security group, S3 bucket, RDS instance and all other dependant aws resources.
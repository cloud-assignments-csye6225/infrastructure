# infrastructure

This repo contains the AWS Cloudformation template to deploy a VPC with 3 subnets, public route table and an Internet Gateway using YAML

Iaac build Instructions:
1. Set the profile and region environment variables through aws cli
   - export AWS_PROFILE=dev
   - export AWS_REGION=us-east-1
2. Use the aws cli and run aws create-stack command to run the infrastructure deployment
   
   - aws cloudformation create-stack --stack-name a3 --template-body file://csye6225-infra.yml --parameters ParameterKey=vpcCIDR,   ParameterValue="10.0.0.0/16" ParameterKey=aSubnetCIDR,ParameterValue="10.0.1.0/24" ParameterKey=bSubnetCIDR,ParameterValue="10.0.2.0/24" ParameterKey=cSubnetCIDR,ParameterValue="10.0.3.0/24"
3. Verify if the stack and the aws resources are reflecting with given configuration on the aws console

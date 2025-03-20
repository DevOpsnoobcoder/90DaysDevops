# AWS VPC Setup with Terraform

This repository provides a Terraform configuration to create a Virtual Private Cloud (VPC) in AWS with the following components:

- **VPC** with a CIDR block `10.0.0.0/16`
- **Public and Private Subnets** across two availability zones.
- **Internet Gateway** for public subnets.
- **NAT Gateway** for internet access from private subnets.
- **Route Tables** with proper routing between subnets and the internet.
- **Security Groups** for web and application servers.

## Prerequisites

Before using this Terraform configuration, ensure you have the following:

- **Terraform** installed: https://www.terraform.io/downloads.html
- An **AWS account** with proper credentials configured on your local machine (you can use AWS CLI for configuration).
- A **text editor** or IDE to modify the Terraform files (e.g., VSCode).

## AWS VPC Design Overview

The AWS VPC setup in this repository includes:

1. **VPC** with CIDR block `10.0.0.0/16`
2. **Public Subnets** (two subnets) for resources needing internet access.
3. **Private Subnets** (two subnets) for resources requiring isolation.
4. **Internet Gateway** to route internet traffic for public subnets.
5. **NAT Gateway** to allow internet access for instances in private subnets.
6. **Security Groups** for controlling inbound and outbound traffic to EC2 instances.

## Terraform Configuration

### File Structure

### Components Included

- **VPC**: `aws_vpc.my_vpc`
- **Public Subnets**: `aws_subnet.public_subnet_1`, `aws_subnet.public_subnet_2`
- **Private Subnets**: `aws_subnet.private_subnet_1`, `aws_subnet.private_subnet_2`
- **Internet Gateway**: `aws_internet_gateway.my_internet_gateway`
- **NAT Gateway**: `aws_nat_gateway.my_nat_gateway`
- **Route Tables**: For public and private subnets.
- **Security Groups**: Web and application security groups for controlled access.

## Setup Instructions

Initialize Terraform:

Initialize Terraform to download the necessary provider plugins.
terraform init

Create an Execution Plan:

Generate a plan to review the resources that will be created.
terraform plan

Apply the Configuration:

Apply the configuration to create the VPC and associated resources.
terraform apply


Confirm the action by typing yes when prompted.
Verify the Resources:

After applying the configuration, log in to the AWS console to verify that the VPC, subnets, internet gateway, NAT gateway, and other resources have been created.

To delete all the resources created by Terraform (including the VPC), run the following command:
terraform destroy

Confirm the destruction by typing yes when prompted.

Security Considerations
Modify the security group rules (web_sg and app_sg) based on your application requirements.

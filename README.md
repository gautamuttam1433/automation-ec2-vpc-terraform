Terraform-AWS-Automator
Project Overview

Terraform-AWS-Automator is an Infrastructure-as-Code (IaC) project that automates the provisioning and management of AWS resources such as Virtual Private Cloud (VPC), EC2 instances, S3 buckets, and Auto Scaling groups using Terraform. This project demonstrates how to efficiently manage AWS infrastructure resources with a consistent and repeatable approach.
Features

    VPC Creation: Automatically creates a Virtual Private Cloud (VPC) for network isolation.
    EC2 Instance Deployment: Provision EC2 instances based on a given AMI ID and instance type.
    S3 Bucket: Creates an S3 bucket for storing and managing data.
    Auto Scaling: Automates scaling of EC2 instances to ensure consistent performance under different workloads.
    Terraform Automation: Simplifies the deployment and management process using Terraform.

Technologies Used

    Terraform: An open-source Infrastructure as Code (IaC) tool used to define and provision AWS infrastructure.
    AWS: Cloud computing services including EC2, S3, VPC, and Auto Scaling.
    GitHub Actions: Continuous Integration/Continuous Deployment (CI/CD) pipeline automation to execute Terraform commands.

Project Structure

├── main.tf              # Main Terraform configuration file to define resources
├── variables.tf         # Terraform variables to parameterize the configuration
├── terraform.tfvars     # Default values for variables
├── output.tf            # Terraform outputs, such as resource IDs
├── README.md            # Project documentation (this file)
├── .github/
│   └── workflows/
│       └── terraform.yml  # GitHub Actions CI/CD workflow

Getting Started

Follow these steps to get your environment set up:
Prerequisites

Before you begin, ensure that you have:

    An AWS account with appropriate IAM credentials (Access Key ID and Secret Access Key).
    Terraform installed on your machine. You can install it by following Terraform's official installation guide.
    AWS CLI configured with your AWS credentials. You can set this up by following the AWS CLI installation guide.

Setting Up Your Project

    Clone the Repository
    Clone the repository to your local machine:

git clone https://github.com/your-username/terraform-aws-automator.git
cd terraform-aws-automator

Configure AWS Credentials
Ensure your AWS credentials are set using either environment variables or the AWS CLI.

export AWS_ACCESS_KEY_ID=your-access-key-id
export AWS_SECRET_ACCESS_KEY=your-secret-access-key

Configure Variables
Set the required variables in the terraform.tfvars file. This file contains values like AMI IDs, instance types, VPC CIDR blocks, and other configurations:

    ami_id = "ami-xxxxxxxxxxxxxxxxx"
    instance_type = "t2.micro"
    subnet_id = "subnet-xxxxxxxxx"
    security_group_id = "sg-xxxxxxxx"

Running Terraform Locally

    Initialize Terraform
    Initialize your working directory with Terraform to download necessary provider plugins:

terraform init

Plan the Changes
Generate and review the execution plan:

terraform plan

Apply the Changes
Apply the configuration to create or update AWS resources:

    terraform apply

GitHub Actions CI/CD

The project includes a CI/CD pipeline configured with GitHub Actions to automate the Terraform deployment process. Once the workflow is triggered, it will run the following steps:

    Initialize Terraform.
    Validate and Plan the infrastructure.
    Apply the changes to AWS resources.

You can trigger the pipeline manually or on any push to your GitHub repository.

The pipeline is defined in .github/workflows/terraform.yml.
Variables

These are the key variables in the variables.tf file:

    create_vpc: A boolean to control whether to create a VPC (default: false).
    create_ec2: A boolean to control whether to create an EC2 instance (default: false).
    create_s3: A boolean to control whether to create an S3 bucket (default: false).
    create_autoscaling: A boolean to control whether to create an Auto Scaling group (default: false).
    ami_id: The AMI ID to be used for EC2 instances.
    instance_type: The EC2 instance type (e.g., t2.micro).
    subnet_id: The subnet ID to associate with the EC2 instances.
    security_group_id: The security group ID to associate with the EC2 instance.
    s3_bucket_name: The name for the S3 bucket.

Outputs

    vpc_id: The ID of the created VPC.
    ec2_instance_id: The ID of the created EC2 instance.
    s3_bucket_name: The name of the created S3 bucket.
    autoscaling_group_name: The name of the created Auto Scaling group.

Troubleshooting

If you encounter any issues during the Terraform process, check the following:

    Missing variables: Ensure all required variables are set in terraform.tfvars or defined in the command line.
    AWS Permissions: Ensure your IAM user has permissions to create the necessary AWS resources.
    Terraform errors: Review the error message returned by Terraform for troubleshooting. You may need to adjust resource configurations based on AWS limits and availability.

Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request. Be sure to follow best practices and ensure your changes are thoroughly tested.

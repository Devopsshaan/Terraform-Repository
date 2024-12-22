Terraform: Create VPC and Launch EC2 Instance with Docker
This repository contains Terraform code to create a VPC component, associate a subnet, and launch an EC2 instance with Docker running on Amazon Web Services (AWS).

Table of Contents
Prerequisites
Getting Started
Commands Overview
Environment Variables
Terraform State Management
Author
Prerequisites
Terraform Installed: Install Terraform on your local machine. Installation Guide
AWS CLI Installed: Install and configure the AWS CLI. Installation Guide
AWS Credentials: Ensure your AWS access key and secret access key are set up for authentication.
Getting Started
Clone the repository:

bash
Copy code
git clone <repository-url>
cd <repository-folder>
Initialize the Terraform working directory:

bash
Copy code
terraform init
Preview the Terraform execution plan:

bash
Copy code
terraform plan -var-file=terraform-dev.tfvars
Apply the Terraform configuration:

bash
Copy code
terraform apply -var-file=terraform-dev.tfvars
Access your EC2 instance with the public IP displayed in the Terraform output. Ensure Nginx is running on port 8080.

Commands Overview
Initialize Terraform
Initialize the Terraform working directory:

bash
Copy code
terraform init
Preview Changes
Preview the planned actions Terraform will take:

bash
Copy code
terraform plan -var-file=terraform-dev.tfvars
Apply Configuration
Apply the configuration and create resources:

bash
Copy code
terraform apply -var-file=terraform-dev.tfvars
Destroy Resources
Destroy a specific resource:
bash
Copy code
terraform destroy -target aws_vpc.myapp-vpc
Destroy all resources defined in the configuration:
bash
Copy code
terraform destroy
Environment Variables
Set environment variables for custom Terraform or AWS configuration.

Set Availability Zone
Before running terraform apply, specify the availability zone:

bash
Copy code
export TF_VAR_avail_zone="eu-west-3a"
AWS Credentials
Set AWS credentials and default region:

bash
Copy code
export AWS_ACCESS_KEY_ID="anaccesskey"
export AWS_SECRET_ACCESS_KEY="asecretkey"
export AWS_DEFAULT_REGION="us-west-2"
Terraform State Management
List Resources in State
Show all resources managed by the current Terraform state:

bash
Copy code
terraform state list
View Specific Resource State
Inspect the current state of a specific resource:

bash
Copy code
terraform state show aws_vpc.myapp-vpc
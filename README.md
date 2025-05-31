# Cloudformation CI/CD Project

This repository contains infrastructure-as-code templates and CI/CD configuration to automate the deployment of an Apache web server using AWS services such as EC2, CodePipeline, S3, and CloudFormation.

## 📁 Repository Structure

# Cloudformation

## 🚀 Deployment Overview

The CI/CD pipeline is designed with the following stages:

1. **Source Stage**  
   GitHub repo triggers the pipeline on push to `main`.

2. **Build Stage (CodeBuild)**  
   - Validates the CloudFormation template  
   - Packages and uploads the processed template to S3 (if needed)

3. **Deploy Stage (CloudFormation)**  
   - Launches an EC2 instance using `ec2-user-data.yaml`  
   - Installs Apache and deploys a static HTML page

## 🔧 Key Files

- `buildspec.yml`:  
  Defines the commands CodeBuild uses to package or validate CloudFormation templates and log the deployment steps.

- `ec2-user-data.yaml`:  
  Provisions an EC2 instance with Apache HTTP Server pre-installed and starts the service on boot.

## ✅ Prerequisites

- IAM roles with appropriate trust and permissions for CodeBuild and CloudFormation
- An S3 bucket named `anjellscloud-pipeline-artifacts`
- A GitHub repository connection set up in AWS CodePipeline
- A VPC with public subnet (`subnet-0466ed668dbd61c3c`)

## 💻 Technologies Used

- AWS EC2
- AWS CloudFormation
- AWS CodePipeline
- AWS CodeBuild
- Ansible (for extended provisioning)
- GitHub

## 👤 Author

**Anjell Hanley**  
Cloud/DevOps Engineer | AWS Certified  
[LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/AnjellCH)

---

### ✅ How to Use

1. Clone this repo
2. Connect GitHub to AWS CodePipeline
3. Ensure `buildspec.yml` and `ec2-user-data.yaml` are in the root of the repo
4. Trigger the pipeline from AWS

---

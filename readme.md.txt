 🚀 Multi-Service CI/CD Deployment Using Jenkins, AWS CloudFormation & CloudWatch

## Overview
Automated CI/CD project using Jenkins, ECS, Docker, Maven, and AWS services including CloudFormation, CloudWatch, and IAM.

## Structure
- **Jenkinsfile** – Main pipeline
- **cloudformation/** – Templates for EC2, IAM, S3 (adjust for ECS if needed)
- **deploy-scripts/** – Script to deploy to EC2
- **monitor/** – Script for CloudWatch log setup

## Usage
1. Configure AWS credentials and region
2. Ensure Jenkins has Docker and AWS CLI support
3. Create pipeline in Jenkins using this repo
4. Monitor ECS deployment and CloudWatch logs
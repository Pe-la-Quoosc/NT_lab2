# NTLab Infrastructure

## Overview

This project uses AWS CloudFormation to deploy a basic AWS infrastructure and AWS CodePipeline to automate the deployment process.

The infrastructure includes:

- VPC
- Public Subnet
- Private Subnet
- Internet Gateway
- NAT Gateway
- Route Tables
- Security Groups
- Public EC2 Instance
- Private EC2 Instance

## Architecture

CodeCommit → CodeBuild → CloudFormation

Source code is stored in AWS CodeCommit. AWS CodeBuild validates the CloudFormation template using cfn-lint and Taskcat. AWS CodePipeline automates the deployment process by updating the CloudFormation stack.

## Repository Structure

```text
.
├── template.yaml
├── buildspec.yml
├── taskcat.yml
└── README.md
```

### template.yaml

CloudFormation template used to provision AWS infrastructure resources.

### buildspec.yml

Build configuration file for AWS CodeBuild.

### taskcat.yml

Configuration file used by Taskcat to validate CloudFormation templates.

## Deployment

1. Push source code to AWS CodeCommit.
2. AWS CodePipeline is triggered automatically.
3. AWS CodeBuild validates the CloudFormation template.
4. AWS CloudFormation creates or updates the stack.

## Stack Name

```text
NTlab
```

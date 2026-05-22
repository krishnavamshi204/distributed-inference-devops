# distributed-inference-devops
Terraform-based distributed inference infrastructure deployment on AWS
Distributed Inference Infrastructure on AWS
Overview

This project demonstrates the setup and deployment of a Distributed Inference Infrastructure using Terraform, AWS EC2, Python workers, and Linux environments.

The assignment focuses on:

Infrastructure provisioning using Terraform
Worker-based distributed inference architecture
AWS EC2 deployment
Linux environment setup
Python dependency management
Infrastructure troubleshooting and debugging

##The infrastructure consists of:

API Server
Caller Worker
Inference Worker

All infrastructure resources were provisioned and managed using Terraform.

##Architecture
Client Request
│
▼
API Server (EC2)
│
▼
Caller Worker (EC2)
│
▼
Inference Worker (EC2)
│
▼
ML Processing / Response

##Tech Stack

Technology Purpose
Terraform Infrastructure as Code
AWS EC2 Compute Infrastructure
Python Worker Runtime
Linux Server Environment
Node.js Runtime Dependencies
Git & GitHub Version Control
Infrastructure Provisioning

##Terraform was used to provision:

VPC
Public Subnet
Security Groups
EC2 Instances
SSH Key Configuration

##Instances Created:

api-server
caller-worker
inference-worker

##Project Structure

distributed-inference/
│
├── terraform-demo/
│ ├── main.tf
│ ├── variables.tf
│ ├── outputs.tf
│ ├── terraform.tfstate
│
├── workers/
│ ├── caller-worker/
│ └── inference-worker/
│
├── screenshots/
│ ├── terraform-init.png
│ ├── terraform-apply.png
│ ├── ec2-running.png
│ ├── worker-setup.png
│ ├── terraform-output.png
│
├── README.md

Terraform Setup
Initialize Terraform
terraform init
Validate Configuration
terraform validate
Apply Infrastructure
terraform apply

Type:

yes
Terraform Outputs
terraform output

Outputs include:

P
Terraform Initialization
Terraform Apply
Terraform Outputs
EC2 Running Instances
SSH Access
Worker Setup
Dependency Installation
Infrastructure Validation

##Challenges Faced:
III SDK / Module Integration Issue

One of the major blockers during the assignment was the integration of the iii SDK required by the inference worker.

While running the worker:

python inference_worker.py

Encountered:

ModuleNotFoundError: No module named 'iii'
Investigation Performed

To troubleshoot the issue:

Verified requirements.txt
Explored repository structure
Checked worker manifest configuration (iii.worker.yaml)
Searched for SDK installation references in the repository
Attempted package installation using pip

Commands used:

pip install iii-sdk
find . -name "_iii_"
cat iii.worker.yaml
Root Cause Analysis

The repository mainly provided:

worker templates
configuration manifests
infrastructure setup

However, the actual iii SDK package was not publicly available through PyPI during implementation.

This caused:

ERROR: No matching distribution found for iii-sdk
Learning Outcome

This issue provided practical exposure to:

dependency troubleshooting
SDK verification workflows
package management debugging
infrastructure-level investigation
real-world DevOps debugging practices

It also highlighted the importance of:

dependency documentation
package availability validation
reproducible environment setup
Current Status

Infrastructure provisioning and worker environment setup were completed successfully.

The remaining limitation was external SDK availability required for complete runtime execution.

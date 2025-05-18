For this project we are working on provisioning infrastuctures for Java and python app. I use gitworkflow automation to provisiong Ec2 severs for the java app and python app. both applications will be running on different server. in the .github/work flow, i have the ci pipeline. GitHub Actions looks specifically into this directory (.github/workflow) to find the yml file and run your automation pipelines. my bootstrap foler contains Separate Initialization from my Main Infrastructure.it consist of hhe S3 bucket for Terraform state is foundational— which we need before before we can run other Terraform scripts that depend on remote state.  In my infra folder, i have the terraform files main.tf, variable.tf and variable.tfvars, which defines the actual infrastructure resources and configurations using Terraform.

repo-root/
├── bootstrap/          # Setup remote backend resources like S3 bucket
│   ├── main.tf
│   ├── variables.tf
│   └── terraform.tfvars
├── main_infra/         # Your actual infrastructure code
│   ├── main.tf
│   ├── variables.tf
│   └── terraform.tfvars
├── .github/workflows/  # GitHub Actions workflows
└── .gitignore

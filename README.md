# Terraform Basics

This repo provides a beginner-friendly guide to using Terraform for managing your infrastructure on AWS. Terraform is an Infrastructure as Code (IaC) tool that enables you to define and manage your infrastructure using code.

## Prerequisites

Before you begin, make sure you have the following:

- An AWS account: You'll need an AWS account to create and manage resources.
- Terraform Installed: Install Terraform by following the instructions in the [official documentation](https://learn.hashicorp.com/tutorials/terraform/install-cli).
- AWS Access Keys: Obtain your AWS access key and secret key to authenticate Terraform with your AWS account.

## Getting Started

1. **Configure AWS Credentials**:

    Create a file named `terraform.tfvars` and add your AWS access and secret keys:

    ```hcl
    access_key = "YOUR_AWS_ACCESS_KEY"
    secret_key = "YOUR_AWS_SECRET_KEY"
    ```

2. **Review and Modify Configuration**:

    Open `variables.tf` and modify default values as per your requirements. These variables will be used throughout your Terraform scripts.

3. **Initialize Terraform**:

    ```bash
    terraform init
    ```

4. **Review the Plan**:

    ```bash
    terraform plan
    ```

    This command shows you the changes Terraform will apply based on your configuration.

5. **Apply Changes**:

    ```bash
    terraform apply
    ```

    This command creates the specified resources based on your configuration.

## Terraform State

Terraform uses a state file (`terraform.tfstate`) to keep track of the resources it manages. This file stores the relationships and metadata of the created resources. **Never delete or modify this file manually**.

## Terraform Variables

Variables in Terraform allow you to parameterize your configurations. The `variables.tf` file defines the variables you'll use in your Terraform scripts. You can provide values for these variables in the `terraform.tfvars` file.

## Terraform.tfvars

The `terraform.tfvars` file holds values for your variables. It allows you to set sensitive information (like access keys) securely without exposing them directly in your configuration files. Make sure to add this file to your `.gitignore` to keep your credentials private.

## Terraform State Backup

Terraform also generates a `terraform.tfstate.backup` file when it updates the state. This is a backup of the previous state and is used to recover the state file in case of errors or accidents. Just like the main state file, **do not modify or delete this backup manually**.

## Clean Up

To destroy the resources created using Terraform, run:

```bash
terraform destroy
```

This command removes all the resources created by your Terraform scripts.

## Learn More

- [Terraform Documentation](https://www.terraform.io/docs/index.html): Official documentation covering all aspects of Terraform.
- [Terraform AWS Provider Documentation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs): Documentation specific to the AWS provider.
- [Terraform Up and Running](https://www.terraformupandrunning.com/): A book by Yevgeniy Brikman that provides in-depth guidance on using Terraform effectively.

## Disclaimer

This repository is for educational purposes and demonstrates basic usage of Terraform. Always be cautious and understand the changes you're making to your infrastructure.

**Note:** This README provides simplified explanations of Terraform basics. Refer to official documentation for comprehensive information.

Feel free to adapt and customize this README to match your repository's structure and your specific use case.

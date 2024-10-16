# Infrastructure as Code with Terraform and Azure

This project utilizes **Terraform** to deploy infrastructure on **Microsoft Azure**, including a virtual machine (VM) equipped with a web server. By defining your infrastructure as code, you can automate deployments, ensure consistency, and manage your resources efficiently.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [1. Clone the Repository](#1-clone-the-repository)
  - [2. Initialize Terraform](#2-initialize-terraform)
  - [3. Review the Deployment Plan](#3-review-the-deployment-plan)
  - [4. Apply the Configuration](#4-apply-the-configuration)
- [Cleanup](#cleanup)
- [Project Structure](#project-structure)
- [Additional Information](#additional-information)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Prerequisites

Before you begin, ensure you have met the following requirements:

- **Terraform Installed:**  
  Download and install Terraform from the [official website](https://www.terraform.io/downloads).

- **Azure CLI Installed and Configured:**  
  Install the Azure CLI from [here](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli) and configure it by running:
  ```bash
  az login
  ```
  This command will open a browser window for you to authenticate with your Azure account.

  - **Azure Credentials Configured:**  
  Ensure your Azure credentials are set up correctly. You can set up a service principal for Terraform by following this guide.
##  Getting Started
  Follow these steps to deploy the infrastructure using Terraform.

1. Clone the Repository  
First, clone the repository to your local machine:

  ```bash
  git clone https://github.com/yourusername/infrastructure-as-code-terraform-azure.git
  ```
Navigate to the project directory:

  ```bash
  cd infrastructure-as-code-terraform-azure
  ```
2. Initialize Terraform  
Initialize the Terraform working directory. This command downloads the necessary provider plugins and prepares the environment.

  ```bash
  terraform init
  ```
3. Review the Deployment Plan  
Before applying the changes, it's good practice to review what Terraform intends to do. This helps prevent unintended modifications.

  ```bash
  terraform plan
  ```
4. Apply the Configuration  
Apply the Terraform configuration to deploy the resources to Azure. This command will prompt you for confirmation before proceeding.

  ```bash
  terraform apply
  ```
  Type yes when prompted to confirm the deployment.

5. Access the Web Server  
After successful deployment, Terraform will output the public IP address of the virtual machine. You can access the web server by navigating to this IP address in your browser.

For example:

  ```arduino
http://<public_ip_address>
  ```
Replace <public_ip_address> with the actual IP provided in the Terraform output.

Cleanup
To remove all the resources that were created by Terraform, execute the following command:

  ```bash
  terraform destroy
  ```
Confirm the destruction by typing yes when prompted. This will delete all the resources defined in your Terraform configuration, ensuring you don't incur unnecessary costs.

Project Structure
Here's an overview of the project's directory structure:

  ```css
infrastructure-as-code-terraform-azure/
├── main.tf
├── variables.tf
├── outputs.tf
├── README.md
   ```
main.tf:  
Contains the primary Terraform configuration for deploying Azure resources.

variables.tf:  
Defines the input variables for the Terraform configuration, allowing for customization.

outputs.tf:  
Specifies the outputs from the Terraform deployment, such as the public IP address.

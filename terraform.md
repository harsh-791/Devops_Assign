
# Terraform & Infrastructure as Code — Revision Notes

## Introduction to Terraform

* **Terraform** is an open-source tool used to manage cloud infrastructure using code.
* Supports multiple providers like **AWS, Azure, and GCP**.
* Follows the **Infrastructure as Code (IaC)** paradigm.

## Key Characteristics

* **Platform Agnostic** → Works across multiple cloud providers.
* **Infrastructure as Code** → Infrastructure defined declaratively using `.tf` files.
* Enables automation, repeatability, and reduced manual errors.

## Terraform Lifecycle Commands

Terraform follows a simple four-step lifecycle:

### 1. `terraform init`

* Initializes the working directory.
* Downloads providers and modules.
* Locks provider versions.

### 2. `terraform plan`

* Compares desired state vs current state.
* Shows execution plan without making changes.
* Used to validate infrastructure changes safely.

### 3. `terraform apply`

* Applies the planned changes.
* Creates, updates, or modifies infrastructure.
* Executes changes in a controlled manner.

### 4. `terraform destroy`

* Deletes all resources managed by Terraform.
* Used for cleanup and decommissioning.

## Advantages of Terraform

* **Automation & Speed** → Faster infrastructure provisioning.
* **Consistency** → Same configuration across environments.
* **Version Control Friendly** → `.tf` files can be tracked in Git.
* **Rollback Capability** → Infrastructure history via code.

## Supporting Tools

### Configuration Management

* Tools like **Ansible, Puppet, Chef** handle software configuration.
* Terraform focuses on infrastructure provisioning.

### Server & Environment Templating

* **Vagrant** → VM-based environments.
* **Docker** → Containerized environments.
* Can complement Terraform-managed infrastructure.

## Practical Use Case

### Example: EC2 Instance Creation

* Define EC2 resource in Terraform `.tf` files.
* Use:

  ```bash
  terraform init
  terraform plan
  terraform apply
  ```
* Terraform state tracks resource changes and dependencies.

## Key Takeaway

Terraform simplifies infrastructure management by making it **declarative, automated, consistent, and auditable**, making it a core DevOps tool.

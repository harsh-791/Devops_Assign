
# AWS & Terraform — Revision Notes

## 1. Subnets in AWS

* **Subnet** → A range of IP addresses inside a VPC.
* **Public Subnet**

  * Connected to an **Internet Gateway**
  * Accessible from the internet
* **Private Subnet**

  * No direct internet access
  * Used for internal services (DBs, backend)

## Terraform Implicit Dependencies

* Terraform automatically determines resource creation order.
* If one resource references another, Terraform builds the dependency graph automatically.
* No need to manually specify dependencies in most cases.

---

## 2. VPC and Network Configuration

* **VPC (Virtual Private Cloud)**

  * Logically isolated virtual network in AWS
* **CIDR Block**

  * Defines IP range of the VPC (e.g., `10.0.0.0/16`)
* **Route Tables**

  * Control how traffic flows within the VPC
  * Routes based on destination IP

---

## 3. Terraform Basics

### State Management

* Terraform tracks infrastructure using **terraform.tfstate**
* State file stores:

  * Resource mappings
  * Metadata
* **Remote State (Best Practice)**

  * Store state in **S3**
  * Use **DynamoDB** for state locking
  * Prevents conflicts in team environments

### Common Terraform Files

* `main.tf` → Core configuration
* `network.tf` → VPC, subnets, gateways
* `compute.tf` → EC2, security groups

---

## 4. Types of IP Addresses

* **Private IP**

  * Used inside VPC
  * Not internet accessible
* **Public IP**

  * Internet accessible
  * Can change on restart
* **Elastic IP**

  * Static public IP
  * Can be reassigned to different resources

---

## 5. EC2 Instance Creation

* EC2 requires an **AMI (Amazon Machine Image)**.
* AMI defines:

  * OS
  * Pre-installed software
* Instances cannot be launched without an AMI.

---

## 6. Variables in Terraform

* **Input Variables**

  * Make configurations reusable
* **Output Variables**

  * Display useful infrastructure info
* **Local Variables**

  * Limited to a specific configuration
  * Improve readability

---

## Key Takeaway

Terraform enables **structured, automated AWS infrastructure management** with clear dependency handling, reusable configurations, and scalable state management—making it essential for modern DevOps workflows.

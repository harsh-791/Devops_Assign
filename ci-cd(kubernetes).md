# CI/CD with Kubernetes — Revision Notes

## Introduction

This class focused on deploying applications to **Kubernetes** using **Continuous Integration (CI)** and **Continuous Deployment (CD)**, which form the backbone of modern DevOps practices.

## Continuous Integration (CI)

* Automates integration of code from multiple contributors.
* Key goals:

  * Frequent code merges
  * Automated builds and tests
  * Always maintain a deployable main branch

## Continuous Deployment (CD)

* Extends CI by **automating deployments**.
* Focuses on:

  * Infrastructure configuration
  * Zero-downtime deployments
  * Automated delivery to production environments

## Kubernetes Environment Setup

### Virtual Machine Setup

* Minimum requirement: **single-node Kubernetes cluster**
* Tools used:

  * **VirtualBox**
  * **Vagrant**
* Vagrant scripts automate VM creation and configuration.

### Kubernetes Installation

* Kubernetes must be pre-installed on the VM.
* Using a pre-built **AMI with Kubernetes installed** can save setup time.

## GitHub Actions in CI/CD

* GitHub Actions enables **automation of CI/CD pipelines** directly from repositories.
* Supports:

  * Build
  * Test
  * Package
  * Release
  * Deploy

## Custom (Self-Hosted) Runners

* Alternative to GitHub-hosted runners.
* Typically configured on **Linux machines**.
* Steps:

  * Register runner using `config.sh`
  * Assign labels
  * Apply security configurations
* Useful for:

  * Custom environments
  * Kubernetes-based deployments

## Project-Based Learning

* Teams implement CI/CD pipelines for real projects.
* Each member is accountable for:

  * Individual contributions
  * Explaining their work during reviews and presentations

## Testing and Quality Assurance

* Multiple testing stages:

  * **System Integration Testing (SIT)**
  * **Performance Testing**
  * **Security Testing**
* Testing pipelines are mostly **automated** to:

  * Reduce errors
  * Improve reliability
  * Ensure consistency

## Practical Considerations

* CI and CD are usually **separate pipelines**.
* Deployment pipelines must be tailored to:

  * Application architecture
  * Infrastructure constraints
* Clear separation improves maintainability and control.

## Key Takeaway

Effective CI/CD with Kubernetes requires **automation, clear pipeline separation, robust testing, and reliable infrastructure setup** to deliver applications safely and efficiently.

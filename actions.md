# GitHub Actions — Revision Notes

## Overview

**GitHub Actions** is a CI/CD platform built into GitHub that enables automation of **build, test, and deployment workflows** directly from a repository.

## Key Features

* **Automated workflows** using community and custom actions
* **Custom pipelines** for build, test, package, and deploy
* **Multi-platform execution** (Linux, Windows, macOS)
* Tight integration with GitHub repositories

## Repository Setup

### Steps

1. Create a GitHub repository (optionally with README, `.gitignore`, license)
2. Clone repository locally:

   ```bash
   git clone <repository-url>
   ```
3. Add project files (e.g., `pom.xml` for Maven projects)

## GitHub Actions Basics

### Workflow Configuration

* Workflow files are stored in:

  ```
  .github/workflows/
  ```
* Written in **YAML**

### Basic Workflow Structure

* **name** → Workflow name
* **on** → Trigger events (e.g., push to `main`)
* **jobs** → Units of work
* **runs-on** → Execution environment
* **steps** → Actions or shell commands

### Sample Workflow

```yaml
name: Java CI with Maven
on:
  push:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-java@v2
        with:
          java-version: '17'
      - run: mvn -B package --file pom.xml
```

## Core Components

* **Actions** → Reusable tasks from GitHub Marketplace
* **runs-on** → OS for job execution (`ubuntu-latest` preferred)
* **Steps** → Ordered execution of actions and commands

## Maven with GitHub Actions

* Use `setup-java` to configure JDK
* Run Maven commands:

  ```bash
  mvn package
  ```
* Produces artifacts (`.jar`, `.war`)
* **Dependency caching** improves build speed and reduces cost

## Cost Management

* Prefer **short-running jobs**
* Use **spot instances** where applicable
* Ensure unused runners are terminated
* Optimize workflow frequency and triggers

## Debugging & Troubleshooting

### Common Issues

* **YAML syntax errors**
* **Incorrect version configurations**
* **Permission issues** for repository or actions

### Best Practices

* Check workflow logs carefully
* Validate tool versions
* Keep workflows minimal and modular

## Key Takeaway

GitHub Actions simplifies CI/CD by enabling **automated, reproducible, and scalable workflows** directly inside GitHub repositories.

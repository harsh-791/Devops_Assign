# GitHub Actions & Docker Integration (Java Maven) — Revision Notes

## Overview

This session focused on integrating **GitHub Actions** and **Docker** in a **Java Maven project** to build an automated CI/CD pipeline with secure secret handling and containerized deployments.

## 1. Git Repository Setup

* Create repository on GitHub, then clone locally:

  ```bash
  git clone <repository-url>
  ```
* Ensure correct structure:

  * `src/`
  * `pom.xml`
* Use standard Git workflow:

  ```bash
  git add .
  git commit
  git push
  ```

## 2. GitHub Actions Basics

* GitHub Actions automates **CI/CD pipelines**.
* Workflows are defined using **YAML** files.
* Workflow files live under:

  ```
  .github/workflows/
  ```
* Triggered on events like:

  * `push`
  * `pull_request`
* YAML syntax is strict → spacing and indentation matter.

## 3. Multi-Job Workflows

* GitHub Actions supports **parallel jobs**.
* Jobs can run on different environments:

  * `ubuntu-latest`
  * `windows-latest`
  * `macos-latest`

## 4. Building with Maven

* Project configuration managed using `pom.xml`.
* CI tasks include:

  * Dependency resolution
  * Compilation
  * Testing
  * Packaging
* Common Maven command:

  ```bash
  mvn clean package
  ```
* Output artifacts:

  * `.jar`
  * `.war`

## 5. Docker Integration

### Docker Setup

* Docker managed independently from Java.
* Key file:

  * `Dockerfile`
* Used to containerize the Java application.

### Docker Hub & Secrets

* Docker images stored in **Docker Hub**.
* Credentials must **never be hardcoded**.
* Use **GitHub Secrets** to store:

  * Docker username
  * Docker password / token

### Image Build & Push

* GitHub Actions automates:

  * Docker image build
  * Tagging
  * Push to Docker Hub

## 6. Testing with Docker

* Basic container tests verify:

  * Image builds correctly
  * Application starts
* Advanced testing requires application-level test logic.

## 7. Security & Quality Checks

### Security Scanning

* Integrate security tools into pipelines:

  * **SAST**
  * **DAST**
* **Trivy** used for Docker image vulnerability scanning.

### Linting & Static Analysis

* Use tools like:

  * **Checkstyle**
  * **CodeQL**
* Ensures code quality and compliance.

## Key Takeaway

Combining **GitHub Actions**, **Maven**, and **Docker** enables a fully automated, secure, and scalable CI/CD pipeline for Java applications.

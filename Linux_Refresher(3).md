# Linux Refresher – Class 3  
## Foundations of DevOps, CI/CD, and Containers

**Course:** Linux Refresher  
**Lecture:** 3  
**Focus:** DevOps fundamentals, CI/CD pipelines, Docker basics, and deployment concepts

---

## Why DevOps Concepts are Covered in a Linux Refresher
Most modern applications run on **Linux servers**.  
DevOps tools like CI/CD pipelines, Docker containers, artifact repositories, and cloud instances are all **Linux-based at their core**.

This class connects Linux fundamentals with:
- Automated builds
- Application deployment
- Containerization
- Production environments

---

## Introduction to DevOps

### What is DevOps?
DevOps is a combination of **practices, culture, philosophies, and tools** that integrate software development (Dev) and IT operations (Ops).

The main goals of DevOps are:
- Faster software delivery
- More reliable deployments
- Better collaboration between teams

DevOps is not only about tools — it strongly emphasizes **automation, shared responsibility, and continuous improvement**.

---

## Why DevOps is Important
In real-world systems, applications must be updated quickly without breaking production.

DevOps helps by:
- Reducing manual work and human errors
- Enabling faster releases
- Improving system stability
- Allowing quick recovery from failures

These skills are highly valued in **production environments and DevOps interviews**.

---

## Software Development Lifecycle (SDLC)

### Traditional Waterfall Model
The waterfall model follows a **linear and sequential workflow**, where each phase must finish before the next begins.

**Phases:**
1. Planning  
2. Requirement Analysis  
3. Design  
4. Coding  
5. Testing  
6. Release  
7. Maintenance  

### Limitations of Waterfall
- Bugs are detected very late
- Difficult to change requirements
- Long release cycles

These limitations led to **Agile and DevOps practices**, which suit modern fast-paced development.

---

## DevOps Lifecycle
DevOps replaces the linear model with a **continuous feedback loop**:

1. Planning  
2. Coding  
3. Build  
4. Test  
5. Release  
6. Deploy  
7. Monitor  

Each stage continuously feeds back into development, making systems **faster and more reliable**.

---

## Shift Left Approach
Shift Left means **moving testing and security earlier** in the development lifecycle instead of waiting until the end.

### Why Shift Left Matters
- Bugs are cheaper to fix early
- Less production failures
- Better code quality
- Developers become responsible for security

Modern DevOps pipelines running on Linux servers heavily follow this approach.

---

## Security Testing in DevOps Pipelines

Security is treated as part of development, not as a separate step.

### Types of Security Testing

#### SAST (Static Application Security Testing)
- Analyzes source code without running it
- Detects insecure methods, SQL injection risks, hardcoded secrets
- Runs early during CI

#### DAST (Dynamic Application Security Testing)
- Tests a running application
- Detects runtime vulnerabilities
- Simulates real attack conditions

#### SCA (Software Composition Analysis)
- Scans third-party libraries and packages
- Identifies known vulnerable dependencies
- Very important since Linux-based applications depend heavily on open-source tools

---

## Example: SQL Injection Vulnerability
Using unsafe query construction (such as Java `Statement`) can lead to SQL injection attacks.

Using `PreparedStatement` prevents this by properly handling user input.

This demonstrates why **secure coding + automated scanning** is critical in CI pipelines.

---

## Continuous Integration (CI)

### What is Continuous Integration?
Continuous Integration is the practice of **frequently integrating code changes** into a shared repository and automatically verifying them.

CI ensures:
- Early bug detection
- Faster feedback for developers
- Consistent and repeatable Linux-based builds

---

## Typical CI Pipeline Flow (Linux-Based)

1. **Code Checkout**
   - Source code fetched from Git repository

2. **Install Dependencies**
   - Linux package managers or tools like Maven/npm download dependencies

3. **Linting**
   - Code quality and style checks
   - Prevents bad code from entering the build

4. **Build / Compile**
   - Source code converted into executable or packaged format

5. **Unit Testing**
   - Tests individual components
   - Mocking is used to isolate dependencies

6. **Run SCA**
   - Scans open-source libraries for vulnerabilities

7. **Run SAST**
   - Scans codebase for security flaws

8. **Artifact Creation**
   - Generates files like:
     - JAR / WAR files
     - Executables
     - Docker images

9. **Artifact Validation**
   - Ensures build correctness and security

10. **Push to Artifact Repository**
   - Stores versioned build outputs safely

---

## Artifacts and Linux Systems
Artifacts are the **final outputs** of a build process.

Examples:
- Binary executables
- Package files
- Docker images

Artifact repositories allow:
- Version control
- Reproducibility
- Traceability across environments

---

## Introduction to Containers and Docker

### Docker and Containers
Docker packages applications into **lightweight Linux containers** that include:
- Application code
- Dependencies
- Runtime environment

This ensures applications behave **consistently across systems**.

### Docker Images
- Immutable build artifacts
- Built in layers
- Layer caching improves build performance

---

## Pushing Docker Images
Once built, Docker images are pushed to a **container registry or artifact repository**.

These images are later pulled during deployment on Linux servers.

---

## Continuous Deployment (CD)

### What is Continuous Deployment?
Continuous Deployment automates application deployment once CI checks pass.

Benefits:
- Faster releases
- Reduced manual steps
- Easier rollbacks
- Consistent production deployments

Deployment strategies depend on risk and environment.

---

## Deployment Environments

### System Integration Testing (SIT)
- First deployment environment after CI
- Tests interaction between multiple services
- Validates system-level behavior

---

## Linux Networking Concepts in Deployment

### Public IP
- Assigned dynamically
- Changes on restart or shutdown

### Elastic IP
- Static and persistent
- Remains unchanged across reboots
- Used for stable production endpoints

---

## Tools Discussed
- **Jenkins / GitHub Actions** – CI/CD automation  
- **Docker** – Containerization  
- **JFrog Artifactory** – Artifact storage  
- **Maven / npm** – Dependency management  
- **Linters** – Code quality tools  
# DevOps Overview and Continuous Integration

## What is DevOps?
DevOps is a combination of **practices, culture, philosophies, and tools** that aim to bridge the gap between software development (Dev) and IT operations (Ops).  
The main goal of DevOps is to **deliver applications faster, more frequently, and with higher reliability**.

DevOps is not just about tools — it heavily focuses on **collaboration**, **automation**, and **ownership** across teams.

---

## Why DevOps is Important
- Faster time to market
- Reduced deployment failures
- Faster recovery from failures
- Better collaboration between teams
- Automation reduces human errors

In real-world systems and interviews, DevOps is valued because it directly impacts **business speed and system stability**.

---

## Software Development Lifecycle (SDLC)

### Traditional Waterfall Model
The waterfall model follows a **linear and sequential approach**, where each phase must be completed before the next begins.

**Phases:**
1. Planning  
2. Requirement Analysis  
3. Design  
4. Coding  
5. Testing  
6. Release  
7. Maintenance  

### Problems with Waterfall
- Late discovery of bugs
- Difficult to change requirements
- Slow delivery cycles

DevOps evolved to solve these limitations by introducing **continuous feedback and automation**.

---

## DevOps Lifecycle
Unlike waterfall, DevOps follows a **continuous cycle**:

1. Planning  
2. Coding  
3. Building  
4. Testing  
5. Release  
6. Deployment  
7. Monitoring  

Each stage continuously feeds back into the next, enabling **faster iterations and improvements**.

---

## Shift Left Approach
The Shift Left approach means **moving testing and security earlier** in the development lifecycle.

### Why Shift Left?
- Bugs are cheaper to fix earlier
- Reduces rework near production
- Improves overall software quality
- Enhances developer responsibility for quality and security

Instead of finding issues at the end, DevOps promotes catching them **as early as possible**.

---

## Security Testing in DevOps

Security is integrated into the pipeline, not added later.

### Types of Security Testing

#### SAST (Static Application Security Testing)
- Analyzes source code without running the application
- Detects issues like SQL injection, hardcoded secrets, insecure methods
- Runs early during CI

#### DAST (Dynamic Application Security Testing)
- Tests the application in a running state
- Identifies runtime vulnerabilities
- Closer to real-world attack scenarios

#### SCA (Software Composition Analysis)
- Scans third-party libraries and dependencies
- Detects known vulnerabilities in open-source components
- Critical because modern applications heavily rely on external libraries

---

## Example: SQL Injection Vulnerability
Using unsafe query construction (e.g., Java `Statement`) can lead to SQL injection attacks.  
Using `PreparedStatement` prevents this by properly handling input parameters.

This highlights the importance of **secure coding + automated security checks** in CI.

---

## Continuous Integration (CI)

### What is CI?
Continuous Integration is the practice of **frequently merging code changes** into a central repository and automatically verifying them through tests and checks.

CI helps catch problems **early and automatically**.

---

## Typical CI Pipeline Steps

1. **Code Checkout**
   - Pull latest code from repository

2. **Install Dependencies**
   - Install required libraries and packages

3. **Linting**
   - Check code style and syntax consistency
   - Improves readability and maintainability

4. **Build / Compile**
   - Convert source code into executable or packaged format

5. **Run Unit Tests**
   - Validate functionality using automated tests

6. **Run SCA**
   - Detect vulnerable third-party libraries

7. **Run SAST**
   - Scan codebase for security vulnerabilities

8. **Docker Image Creation**
   - Package application into a container

9. **Docker Image Validation**
   - Ensure image correctness and security

10. **Push Artifact**
   - Store build output in artifact repository

---

## Continuous Deployment (CD)
Once code passes CI, it moves toward deployment.

- CD automates application deployment
- Reduces manual intervention
- Allows faster and safer releases
- Rollbacks become easier

In real systems, CD may stop at staging or go fully to production depending on risk tolerance.

---

## Tools Mentioned in Class
- **Jenkins / GitHub Actions** – CI/CD automation
- **Docker** – Containerization
- **JFrog Artifactory** – Artifact storage
- **Maven / npm** – Dependency management
- **Linters** – Code quality checks

---

## Project Expectations
- Implement a CI pipeline for a project
- Understand each pipeline stage clearly
- You may use existing code, but **must be able to explain design choices**
- Focus on reasoning, not just implementation

This is especially important for **DevOps interviews and real-world roles**.

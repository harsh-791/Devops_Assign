# Software Development & DevOps — Revision Notes

## Evolution of Software Development

* **Waterfall Model**

  * Sequential and rigid
  * Late feedback and slow releases
* **PLP (Predictable Launch Process)**

  * Structured release planning
  * More predictable than waterfall
* **Agile Methodology**

  * Iterative development
  * Faster feedback and adaptability
* **CI/CD**

  * Automation-driven modern development approach

## CI/CD Overview

* **Continuous Integration (CI)**

  * Focuses on frequent code integration and validation
* **Continuous Delivery / Deployment (CD)**

  * Focuses on automated testing and safe release to production

## Continuous Integration (CI) Steps

1. Code check-in
2. Linting
3. Dependency download
4. Software Composition Analysis (SCA)
5. Static Application Security Testing (SAST)
6. Packaging (JAR, WAR, etc.)
7. Unit testing
8. Dockerization
9. Container testing
10. Image scanning
11. Push to artifact repositories

## Continuous Delivery / Deployment (CD) Steps

1. System Integration Testing (SIT)
2. Security testing
3. Performance testing
4. NLP integration testing
5. A/B testing
6. Penetration testing

## DevOps vs DevSecOps

### DevOps Engineers

* Focus on:

  * Automation
  * CI/CD pipelines
  * Infrastructure and deployments
* Security often added later

### DevSecOps Engineers

* Security integrated **from the start**
* Automate security checks in CI/CD
* Treat security as **shared responsibility**

### Cybersecurity vs DevSecOps

* **Cybersecurity** → Reactive, policy-driven
* **DevSecOps** → Proactive, automated, pipeline-integrated

## Types of Testing

* **Unit Testing** → Tests individual components
* **Integration Testing** → Tests component interaction
* **Performance Testing** → Load and stress testing
* **Security Testing** → Vulnerability detection

## Feature Flagging

* Enables controlled feature releases
* Allows:

  * Gradual rollout
  * Quick rollback
  * Safer experimentation

## Advantages of DevOps

* Faster and frequent releases
* Improved software quality
* High automation
* Consistency across environments
* Enhanced security through early integration

## Importance of Security

* Security must be embedded throughout the SDLC
* Early detection reduces cost and risk
* DevSecOps ensures secure-by-design systems

## Key Takeaway

Modern software development relies on **CI/CD, automation, and integrated security** to deliver fast, reliable, and secure applications.

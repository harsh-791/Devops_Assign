# Docker & Container Technology — Revision Notes

## Introduction to Containers

* Containers package an application with its dependencies into a **standardized, isolated unit**.
* They provide **consistent environments** across development, testing, and deployment.
* Multiple containers run on a **shared OS kernel**.

## Historical Background

* Early isolation concepts existed with **Unix `chroot`**, which created filesystem-level isolation.
* Modern containers extend this idea with **stronger isolation and resource control**.

## Docker Containers

* A **Docker container** is a lightweight, executable package containing:

  * Application code
  * Runtime
  * Libraries and system tools
* Containers **do not include a full OS**; they share the host kernel.

## Containers vs Virtual Machines

* **Lightweight & Fast**: Containers start faster and use fewer resources than VMs.
* **Isolation Mechanism**:

  * Containers → Linux namespaces & cgroups
  * VMs → Hypervisors + full guest OS

## How Containers Work

### Namespace Isolation

Provides separation for:

* Processes (PID)
* Hostnames
* Networking
* Users
* IPC
* File systems

### Control Groups (cgroups)

* Limit and allocate **CPU, memory, and other resources**
* Prevent containers from interfering with each other

## Docker and the Kernel

* On **Linux**: Docker runs directly using the host kernel.
* On **Windows/macOS**: Docker uses a lightweight Linux VM to enable container support.

## Cross-Platform Container Execution

* **Linux** → Native container execution
* **Windows/macOS** → Containers run inside a Linux VM

## Ephemeral Nature of Containers

* Containers are **temporary and disposable**.
* Designed to be:

  * Started
  * Stopped
  * Destroyed easily
* Applications should be **stateless** or store data externally.

## Networking and Port Mapping

* Containers have isolated networking.
* **Port mapping** allows host-to-container communication.
* Ensures controlled and secure access to containerized applications.

## Conclusion

Docker and container technology enable **portable, scalable, and efficient** application deployment. Understanding container isolation, kernel interaction, and lifecycle is essential for modern software engineering.


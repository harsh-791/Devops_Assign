# DevOps Class 5 — Docker Basics & Containerization

## 1. Topics Covered

* What is Docker
* Containers and images
* Containers vs Virtual Machines
* Docker client and daemon
* Docker Hub
* Docker workflow
* Running containers
* Interactive containers
* Volumes and networking (introduction)
* Container isolation
* Docker and host OS relationship

---

## 2. Introduction to Docker

* Docker is a platform for creating and managing containers.
* It allows packaging applications along with all their dependencies into a single unit called a **container**.
* The idea is: if the application runs inside a container, it can run anywhere Docker is installed.

---

## 3. Docker Philosophy

> If it fits, it ships.

* If the application fits inside a Docker container, it can be shipped and run on any machine with Docker.
* No dependency or environment issues across systems.

---

## 4. Containers

* Containers are lightweight, portable, and self-sufficient.
* They include:

  * Application code
  * Runtime
  * Libraries
  * Dependencies
  * Settings
* Containers share the **host OS kernel** but run in isolated user space.
* Much lighter than virtual machines.

---

## 5. Images

* Docker images are **read-only templates** used to create containers.
* Images contain:

  * Application
  * Dependencies
  * Required configuration
* Containers are always created from images.

---

## 6. Containers vs Virtual Machines

### Containers

* Lightweight
* Share host OS kernel
* Fast startup
* No full OS inside

### Virtual Machines

* Heavyweight
* Each VM has its own OS
* Slower startup
* Needs hypervisor

---

## 7. Docker Daemon and Docker Client

### Docker Daemon

* Background service running on the host machine.
* Manages:

  * Containers
  * Images
  * Networks
  * Volumes
* Listens for Docker API requests.

### Docker Client

* Command-line tool used by the user.
* Sends commands to Docker daemon.
* Client and daemon can be on same or different machines.

---

## 8. Docker Hub

* Cloud-based repository for Docker images.
* Default source for images.
* If an image is not available locally, Docker pulls it from Docker Hub.

---

## 9. Docker Workflow

1. User runs a Docker command using Docker client
2. Client sends request to Docker daemon
3. Daemon checks if image exists locally
4. If not:

   * Pulls image from Docker Hub
5. Daemon creates container from the image
6. Container starts running

---

## 10. Running Docker Containers

### Basic run

```bash
docker run ubuntu
```

### Interactive mode

```bash
docker run -it ubuntu /bin/bash
```

Flags:

* `-i` → interactive
* `-t` → terminal

---

## 11. Important Docker Commands

```bash
docker run <image>
docker images
docker ps
docker pull <image>
```

* `docker run` → create and start container
* `docker images` → list local images
* `docker ps` → list running containers
* `docker pull` → download image from Docker Hub

---

## 12. Volumes and Networking (Introduction)

### Volumes

* Used for **persistent storage**
* Data is stored outside container filesystem
* Data is not lost when container is deleted

### Networking

* Docker provides its own networking
* Containers can communicate with:

  * Other containers
  * Host machine
  * External systems

---

## 13. Container Isolation

* Each container runs in an isolated environment.
* Isolation includes:

  * File system
  * Processes
  * Network
* Multiple containers can safely run on the same host.

---

## 14. Docker and Host System

* Docker does not have its own OS.
* Containers use the **host OS kernel**.
* This is why Docker containers are:

  * Fast
  * Lightweight
  * Efficient

---

## 15. Important Points

* Containers are created from images
* Images are read-only templates
* Docker client talks to Docker daemon
* Docker Hub stores images
* Containers share host OS kernel
* Containers are lighter than VMs
* Docker provides isolation without full OS

---

## 16. Summary

* Docker is used for containerization
* Containers package app + dependencies
* Images are used to create containers
* Docker Hub is the image repository
* Containers are lightweight and fast
* Docker uses host OS kernel


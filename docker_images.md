# Docker — Software Engineering Revision Notes

## Introduction to Docker

Docker is a platform that automates **building, deploying, scaling, and running applications** using containers. It simplifies application management through image-based packaging and standardized environments.

## Docker Images vs Containers

* **Docker Image**
  A packaged, immutable environment containing the application, runtime, libraries, and dependencies. Images act as the blueprint for containers.
* **Docker Container**
  A running instance of an image. Containers are lightweight, isolated, and share the host OS kernel, making them faster than virtual machines.

## Core Docker Commands

* **docker build**
  Builds an image from a Dockerfile.
  `-t` is used to tag images (tags must be lowercase).
* **docker run**
  Starts a container from an image.
  Common flags:

  * `-d` → detached mode
  * `-p` → port mapping

## Dockerfile Essentials

* **FROM**
  Defines the base image.
* **RUN**
  Executes commands during image build.
  Each RUN creates a new image layer.
* **CMD vs ENTRYPOINT**

  * `CMD` → default command, can be overridden
  * `ENTRYPOINT` → fixed command, not overridden by arguments

## Advanced Concepts

* **Multi-stage Builds**
  Use multiple build stages to reduce final image size by keeping only required artifacts.
* **Copy-On-Write (CoW)**
  Optimizes storage and performance by copying layers only when modifications occur.

## Performance Optimization

* **Reduce Layers**
  Combine commands using `&&` to minimize layers.
* **Optimize Base Images**
  Use smaller base images (e.g., JRE instead of JDK for Java production builds).

## Practical Example

* Java application built using:

  * JDK image in build stage
  * JRE image in final stage
    Result: smaller, production-ready image.

## Tools & Environment

Hands-on practice included:

* Docker installation
* Building images
* Running containers
* Deploying applications locally

## Conclusion

Docker enables efficient, portable, and scalable application deployment. Mastery of images, Dockerfiles, and optimization techniques is essential for modern software engineering workflows.
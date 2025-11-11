
# Docker & Containerization — Minimal Revision Notes

## Docker Basics

* **Docker** is a platform to **build, ship, and run applications** using containers.
* It separates **application** from **infrastructure**, enabling faster and consistent deployments.

## Containers

* Containers package the **app + dependencies** together.
* Ensures the application runs the **same across environments**.
* Lighter than VMs since they **share the host OS kernel**.

## Core Docker Commands

* `docker run` → Start a new container
  Example: `docker run -it ubuntu bash`
* `docker exec` → Run command inside an existing container
  Example: `docker exec -it <container_id> bash`
* `docker ps` → List running containers
* `docker container inspect <id>` → View container details (IP, config)

## Docker Images

* Images are created from containers or Dockerfiles.
* `docker images` → List images
* `docker commit <container_id> <image_name>` → Create image from container

## Docker Hub

* `docker push <image_name>` → Push image to Docker Hub
* Image name must start with **Docker Hub username**

## Networking

* Containers have their own IPs.
* Use `docker container inspect` to find IP.
* Containers can communicate using tools like `curl`.

## Dockerfile & Layers

* Dockerfile defines **step-by-step image creation**.
* Each instruction creates a **new layer**.
* Layer caching improves build efficiency.

## Modes

* **Attached mode** → foreground
* **Detached mode (`-d`)** → background execution

## Key Advantages

* Faster than VMs
* No full OS overhead
* Efficient and portable


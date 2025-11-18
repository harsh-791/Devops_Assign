# Docker Volumes — Revision Notes

## What are Docker Volumes

* Docker volumes provide **persistent storage** for containers.
* Data stored in volumes **survives container deletion**.
* Volumes are **independent of container lifecycle** and can be shared.

## Why Volumes are Important

* Essential for **stateful applications** (e.g., databases).
* Decouples **application logic from storage**.
* Enables safer container restarts and scaling.

## Containers and Data

* Containers are **ephemeral** by design.
* Without volumes, container data is lost on removal.
* Each container has a **writable layer**, but it is not meant for persistence.

## Types of Docker Volumes

### Named Volumes

* Created and managed by Docker.
* Reusable across containers.
* Stored under `/var/lib/docker/volumes/`.

### Anonymous Volumes

* Automatically created.
* No user-defined name.
* Not reusable or easily manageable.

### Bind Mounts

* Direct mapping to host filesystem paths.
* Offers flexibility but requires manual permission management.
* Less portable than volumes.

## Common Use Cases

* **Database persistence** across container restarts.
* **Shared data access** between multiple containers.
* Configuration and logs management.

## Volume Management Commands

* Create volume:

  ```bash
  docker volume create <volume_name>
  ```
* Inspect volume:

  ```bash
  docker volume inspect <volume_name>
  ```
* Attach volume to container:

  ```bash
  docker run -v <volume_name>:<container_path> <image>
  ```
* Read-only volume:

  ```bash
  docker run -v <volume_name>:<container_path>:ro <image>
  ```

## Key Takeaway

Docker volumes ensure **data durability, sharing, and reliability** in containerized applications.

# Kubernetes — Revision Notes

## Overview

Kubernetes is an open-source platform used to **deploy, scale, and manage containerized applications** across clusters. It provides automation, resilience, and scalability for distributed systems.

## Pods

* **Pod** is the smallest deployable unit in Kubernetes.
* A pod contains **one or more containers** scheduled together.
* Control Plane schedules pods; **worker nodes execute them**.

## Kubernetes Architecture

Kubernetes is divided into **Control Plane** and **Data Plane**.

### Control Plane

* **API Server**
  Entry point for all cluster operations (REST-based).
* **etcd**
  Distributed key-value store holding cluster state.
* **Controller Manager**
  Ensures desired state (e.g., correct number of replicas).
* **Scheduler**
  Decides which node a pod should run on.

### Data Plane (Worker Nodes)

* **Kubelet**
  Ensures containers in pods are running.
* **CRI (Container Runtime Interface)**
  Manages container lifecycle (Docker, containerd, etc.).
* **Kube-Proxy**
  Handles networking and service routing on nodes.

## Key Kubernetes Features

* **Automatic Bin Packing**
  Schedules pods based on available resources.
* **Self-Healing**
  Restarts failed containers and reschedules pods.
* **Horizontal Scaling**
  Scale pods manually or automatically.
* **Service Discovery & Load Balancing**
  DNS-based service access and traffic distribution.
* **Automated Rollouts & Rollbacks**
  Zero-downtime application updates.
* **Secrets & Config Management**
  Secure handling of credentials and configs.
* **Batch Execution**
  Support for jobs and cron jobs.

## Scaling in Kubernetes

* **Horizontal Pod Autoscaler (HPA)**
  Scales pod replicas based on metrics.
* **Vertical Pod Autoscaler (VPA)**
  Adjusts CPU and memory of pods.
* **Cluster Autoscaler**
  Scales nodes based on scheduling needs.

## Practical Insights

* **Certificate Management**
  Dynamic certificate handling improves security.
* **Pod Lifecycle**
  Deleting a pod terminates containers and frees resources.

## Conclusion

Kubernetes provides a powerful framework for **automated container orchestration**, enabling efficient management of cloud-native applications at scale.


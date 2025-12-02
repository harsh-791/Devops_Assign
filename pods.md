# Kubernetes Class — Revision Notes

## Overview

The class focused on **hands-on Kubernetes setup** and understanding its **core architecture**, including master–worker configuration, pods, namespaces, and networking.

## Kubernetes Nodes Setup

* Cluster set up using **three machines**:

  * **Master Node** → Control plane responsibilities
  * **Worker Nodes** → Run application workloads
* Master node prepared using **kubeadm** after prerequisite installations.

## Master Node Initialization

* Switched to root user using `sudo su`
* Initialized cluster using:

  ```bash
  kubeadm init
  ```
* This sets up core components:

  * API Server
  * etcd
  * Controller Manager
  * Scheduler

## Pods

### What is a Pod

* Smallest deployable unit in Kubernetes.
* Can contain **one or more containers**.

### Pod Characteristics

* **Co-located** → Containers share networking and storage.
* **Co-scheduled** → Containers always run on the same node.

## Kubernetes Architecture

### Control Plane

* **API Server** → Entry point for all operations
* **etcd** → Stores cluster state
* **Controller Manager** → Maintains desired state
* **Scheduler** → Assigns pods to nodes

### Data Plane

* Worker nodes run applications.
* Node components execute workloads assigned by the control plane.

## kubectl and API Server

* `kubectl` communicates with the **API Server** using REST.
* API Server handles:

  * Authentication
  * Authorization
  * Validation
* Cluster state is stored in **etcd**.

## Pod Deployment and Management

* Pods created and managed using `kubectl`.
* Important commands:

  ```bash
  kubectl get pods
  ```
* Used to monitor pod status and health.

## Namespaces

* Namespaces provide **logical isolation** of resources.
* Default namespaces include:

  * `default`
  * `kube-system`

## Networking

* **CoreDNS** provides internal DNS resolution.
* Requires a **network plugin** (e.g., Weave).
* Scheduling decisions depend on **CPU and RAM availability** on nodes.

## Conclusion

Understanding Kubernetes architecture, pod lifecycle, namespaces, and networking is essential for deploying and managing **microservices-based applications** effectively.


# Kubernetes Core Concepts — Revision Notes

## 1. Kubernetes Overview

* Kubernetes is an **open-source container orchestration platform**.
* Automates **deployment, scaling, and operations** of containerized applications across clusters.

## 2. Pods

* **Pod** is the smallest deployable unit in Kubernetes.
* Contains **one or more containers**.
* Containers in a Pod:

  * Share the **same IP address**
  * Share **port space**
  * Can communicate locally

### Pod Characteristics

* **Co-located** → Scheduled on the same node
* **Shared networking** → One IP per Pod

## 3. ReplicaSets

* Ensures a **fixed number of Pods** are always running.
* Automatically recreates Pods on failure.
* Supports **scale-in and scale-out**.
* Recommended even for a single Pod for fault tolerance.

## 4. Deployments

* Manage Pods and ReplicaSets declaratively.
* Provide:

  * Easy scaling
  * Rolling updates
  * Rollbacks
* Internally control ReplicaSets and Pods.

## 5. Services

* Provide a **stable network endpoint** for Pods.
* Abstract Pod IP changes.

### Types of Services

* **ClusterIP**

  * Internal-only access
* **NodePort**

  * Exposes service on each node’s IP and port
  * Automatically creates a ClusterIP

### Service Features

* **Service discovery** via labels
* **Load balancing** across Pods

## 6. Load Balancers

* Distribute traffic across multiple Pods.
* **Internal LB** → Inside the cluster
* **External LB** → Handles internet-facing traffic

## 7. Kubernetes YAML Files

Kubernetes objects are defined using YAML with:

* **apiVersion** → API version
* **kind** → Object type
* **metadata** → Name, namespace, labels
* **spec** → Desired state

## Key Takeaway

Pods run applications, ReplicaSets maintain availability, Deployments manage lifecycle, and Services expose applications reliably.

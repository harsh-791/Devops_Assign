
# Kubernetes Horizontal Pod Autoscaler (HPA) — Revision Notes

## Overview

**Horizontal Pod Autoscaler (HPA)** automatically scales the **number of pod replicas** based on observed CPU usage or other metrics. It helps maintain performance while optimizing resource usage.

## What is HPA

* HPA adjusts replicas for:

  * Deployments
  * ReplicaSets
  * StatefulSets
* Scaling is **automatic**:

  * Scale up on high load
  * Scale down on low load
* Most commonly based on **CPU utilization**

## Horizontal Scaling Concept

* Scaling happens by **adding or removing pods**.
* Similar to adding more people to share workload when demand increases.

## Prerequisites for HPA

* **Kubernetes cluster** (commonly via `kubeadm`)
* **Metrics Server**

  * Collects CPU and memory usage
  * Required for HPA decisions

## Kubernetes Components Involved

* **kubeadm** → Cluster initialization
* **kubectl** → Cluster management CLI
* **kubelet** → Node-level agent
* **Metrics Server** → Supplies metrics to HPA

## Important Commands

* Apply resources:

  ```bash
  kubectl apply -f <file.yaml>
  ```
* Manually scale replicas:

  ```bash
  kubectl scale --replicas=<number> <resource>/<name>
  ```
* View resource usage:

  ```bash
  kubectl top pods
  kubectl top nodes
  ```
* Monitor objects:

  ```bash
  kubectl get pods
  kubectl get nodes
  ```

## Deploying HPA — High Level Steps

1. Create a **Deployment**
2. Install **Metrics Server**
3. Create **HPA resource**
4. Define:

   * Min replicas
   * Max replicas
   * CPU utilization threshold (e.g., 50%)

## HPA Behavior

* When CPU usage exceeds threshold:

  * Pods scale up automatically
* When usage drops:

  * Pods scale down
* Scaling can be observed **in real time**

## Resource Configuration

* **Requests** → Guaranteed resources
* **Limits** → Maximum allowed usage
* HPA relies heavily on **proper resource requests**

## Troubleshooting

* Missing metrics → HPA will fail
* Ensure Metrics Server is running
* Use `kubectl top` to validate metrics availability

## Key Takeaway

HPA enables **automatic, demand-based scaling**, improving availability and efficiency without manual intervention.

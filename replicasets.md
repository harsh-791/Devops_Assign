
# Kubernetes Pods & ReplicaSets — Revision Notes

## Kubernetes YAML Structure

Most Kubernetes YAML files contain four main sections:

* **apiVersion** → API version for backward compatibility
* **kind** → Type of object (Pod, ReplicaSet, Deployment, etc.)
* **metadata** → Object information (name, labels)
* **spec** → Desired state of the object

## Pods

* Smallest deployable unit in Kubernetes.
* Contains **one or more containers**.
* Containers in a pod are:

  * **Co-located**
  * **Co-scheduled**
  * Share network and resources
* If a container crashes, Kubernetes automatically replaces it.

## YAML Syntax Basics

* **Key–Value** → `key: value`
* **List** → `- item`
* **Map** → Nested key–value structures

## ReplicaSets

### Purpose

* Ensures a **fixed number of pod replicas** are always running.
* Automatically replaces pods if they fail or nodes go down.

### ReplicaSet YAML Structure

* `kind: ReplicaSet`
* `replicas` → Number of pod instances
* `selector` → Matches labels of managed pods
* `template` → Pod definition
* Labels are used to group and manage pods.

## Kubernetes Internal Workflow

* **API Server** → Validates and stores requests
* **etcd** → Stores cluster state
* **Scheduler** → Assigns pods to nodes
* **Kubelet** → Runs and monitors pods on nodes
* **Controllers** → Ensure desired state is maintained

## Pod Lifecycle & Recovery

* ReplicaSet controller continuously compares:

  * **Desired state** vs **Current state**
* On failure, new pods are created automatically to restore balance.

## Common kubectl Commands

```bash
kubectl apply -f <file>
kubectl delete -f <file>
kubectl get <resource>
```

## Key Takeaway

Pods define **what runs**, ReplicaSets ensure **how many run**, and Kubernetes continuously works to keep the system in the desired state.

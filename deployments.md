
# Kubernetes Deployments — Revision Notes

## Overview

Kubernetes **Deployments** build on Pods and ReplicaSets to manage application lifecycles. They enable **scaling, rolling updates, and rollbacks** using declarative configurations.

## Pods and Containers

* **Pod** is the smallest deployable unit in Kubernetes.
* A pod can contain **one or more containers**.
* Containers are lightweight and efficient, inheriting core benefits of containerization.

## ReplicaSets

* Ensure a **fixed number of pod replicas** are always running.
* Automatically replace failed pods or pods lost due to node failures.
* Maintain the **desired state** of the application.

## Deployments

* A **Deployment** manages ReplicaSets.
* Provides:

  * Declarative updates
  * Rolling updates
  * Rollbacks
* Deployment controller updates pods and ReplicaSets automatically.

## YAML Configuration

* Deployments and ReplicaSets are defined using YAML.
* Structure is similar; the key difference is the **kind** field.

### Example Deployment YAML

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.16.1
```

## Scaling and Rollouts

* **Scaling**: Change replica count using `kubectl scale`.
* **Rolling Updates**:

  * Default strategy for deployments
  * Updates pods gradually
  * Ensures **zero downtime**

## Upgrade and Rollback

* Deployments support **version upgrades**.
* Rollbacks allow reverting to previous stable versions.
* Critical for CI/CD pipelines and safe releases.

## Best Practices

* Use **declarative YAML** for all deployments.
* Store configurations in **version control**.
* Use **namespaces** for environment isolation.
* Continuously monitor **desired vs actual state**.
* Avoid imperative commands in production.

## Key Takeaway

Deployments provide a reliable and flexible way to manage application updates, scaling, and recovery in Kubernetes.

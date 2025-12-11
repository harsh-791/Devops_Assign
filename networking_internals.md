
# Kubernetes Networking Internals — Revision Notes

## Overview

Kubernetes networking enables **seamless communication** between containers, pods, services, and nodes. It abstracts complex networking using plugins and core components.

## 1. Container-to-Container (Same Pod)

* Containers in a pod share the **same network namespace**.
* Communicate using **localhost** and standard ports.
* Pod acts as a **single network entity**.
* Similar to multiple processes running on the same machine.

## 2. Pod-to-Pod (Same Node)

* Pods on the same node communicate via a **virtual network**.
* Managed by **CNI (Container Network Interface) plugins**.
* Network plugin allocates IPs and routes traffic correctly.

## 3. Pod-to-Pod (Different Nodes)

* Communication across nodes handled by:

  * Network plugins
  * **iptables rules**
* Traffic is routed through the host network.
* **kube-proxy** maintains and updates routing rules.

## 4. Pod-to-Service Communication

* **Services** provide a stable endpoint for pods.
* Each service gets a **ClusterIP**.
* Traffic is load-balanced across matching pods.

### Service Discovery

* **CoreDNS** maps service names to IPs.
* Pods access services using **DNS names**, not IPs.
* Service endpoints dynamically map services to pods.

## Key Components

* **kube-proxy** → Manages IP tables and routing
* **CoreDNS** → Handles DNS-based service discovery
* **CNI Plugins** → Enable pod networking

## Useful Commands

```bash
kubectl get svc
kubectl describe svc
```

## Key Takeaways

* Kubernetes networking abstracts complexity while ensuring scalability.
* Services decouple pod lifecycles from networking.
* CoreDNS and kube-proxy are critical for discovery and load balancing.

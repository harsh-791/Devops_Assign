
# Docker Networking — Revision Notes

## Overview

Docker networking enables **communication between containers**, and between containers and the external world. It abstracts complex networking concepts while remaining configurable.

## IP Addresses

* Every container gets a **unique IP address** within its Docker network.
* IPs allow containers to communicate with each other.

## Subnetting Basics

* Subnetting divides a network into **smaller logical networks**.
* Uses **CIDR notation** (`/24`, `/26`, etc.).
* Example:
  `192.168.10.0/24` → 256 IP addresses (`2^8`).

## Network ID & Broadcast ID

* **Network ID** → first IP in the subnet (identifies the network).
* **Broadcast ID** → last IP in the subnet (used to reach all hosts).

## Docker Bridge (docker0)

* Docker creates a default bridge called **docker0**.
* Acts like a **virtual switch**.
* Each container:

  * Has an `eth0` interface
  * Connected to docker0 via a **veth pair**

## Default Bridge Network

* Containers run in the default bridge unless specified otherwise.
* Containers can communicate using **IP addresses**.
* Example:

  ```bash
  docker run -d nginx
  ```

## Custom Bridge Networks

* Create custom networks for better isolation:

  ```bash
  docker network create -d bridge my_bridge
  ```
* Supports:

  * Custom subnets
  * Gateways
  * Cleaner container communication

## Container Communication

* Containers in the **same network** can talk directly.
* Docker manages routing using virtual bridges and network namespaces.

## Practical Subnet Example

Splitting a network:

* Engineering → `192.168.10.0/26`
* HR → `192.168.10.64/26`
* Reception → `192.168.10.128/26`

## Troubleshooting

* Use:

  ```bash
  docker inspect <container>
  ```
* Helps view:

  * IP address
  * Network configuration
  * Connected networks

## Summary

Docker networking simplifies container communication using **bridges, subnets, and virtual interfaces**. Understanding `docker0`, subnetting, and custom networks is essential for scalable containerized applications.

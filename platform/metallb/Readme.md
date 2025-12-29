# MetalLB Setup Documentation

This repository contains documentation related to setting up **MetalLB** in a Kubernetes cluster.

The purpose of this document is to capture the configuration and decisions made while enabling `LoadBalancer`-type services in a bare-metal Kubernetes environment, where no cloud provider load balancer is available.

> This documentation was written while working with a **single-node Kubernetes cluster running on a Raspberry Pi**. The setup reflects a homelab-style environment and may need minor adjustments for multi-node clusters or different network layouts.

This README is meant to serve as:

* A reference for future self
* A reproducible note for similar homelab setups

---

The sections below document the actual setup used.

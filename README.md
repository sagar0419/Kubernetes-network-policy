# Kubernetes Network Policy.
Kubernetes Network Policy is namespace scoped. Policies are applied to pods using label selectors. Policy rules can specify the traffic that is allowed to/from pods, namespaces, or CIDRs.

## Description.
- This repo contains code which will only allow frontend and backend namespace to communicate. It will also allow communication from the frontend and backend namespace to the kube-dns pod running in the kube-system namespace. 
- Pods running in the Kubernetes cluster use the kube-dns service for resolving service names to IPs.
- Network Policy files in this repo can be used in Calico and Cilium CNI as both CNI support Kubernetes Network Policy.

## Manifest.
As we know that Kubernetes network policy is namespace scoped, so we have created 2 manifest files, one for the frontend namespace and one for the backend namespace.
frontend.yaml file contains network policy for frontend namespace and backend.yaml file contains network policy for backend namespace.

## Default deny.
deny.yaml file contains network policy which will block all Ingress and Egress traffic in a namespace.

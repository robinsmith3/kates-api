# Build a complete infrastructure to run API apps
- mimic a cloud infrastructure
- as secure as possible
- as simple as possible for re-gen
- use Teraform and Ansible

## Config

## Build an LXD installation for k8s cluster node VM's
Hosted on a bare metal lab server (Ubuntu 24.04)

## Build a bridge br0 bridge onn the host using a static IP
- use router config to map static ip's on cluster nodes
- do not try to explicitly set the cluster nodes to static IP with lxc config
- https://grok.com/share/c2hhcmQtMg%3D%3D_bae421d9-4a6f-4cb0-9401-489ce6c4064d

## Build a 3 node k8s cluster from the LXC nodes

## Build the edge services infrastructure
- add a MetalLB load balancer to serve the ingress
- add an Nginx Ingress controller to route the apps
- https://grok.com/share/c2hhcmQtMg%3D%3D_ab0ba4e3-176b-4e96-a5a4-63ab1c70ed42


## Config

### For a br0 bridge using static IP for host and VM's
https://grok.com/share/c2hhcmQtMg%3D%3D_bae421d9-4a6f-4cb0-9401-489ce6c4064d

I have an Ububtu host system running LXD with 3 ubuntu VM's
The host is 192.168.1.10, node1 is 11, node2 is 12, node3 is 13
All cluster nodes are attached to a bridge br0 on the host
The default lxdbr0 was deleted
Connectivity is all fine
I already have a base kubernetes cluster running on all 3 nodes, the control plane is on node1
I want to install metallb and nginx ingress for use with future apps on the cluster
Please can you help?

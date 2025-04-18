# Build a complete bare metal infrastructure to run API's
- mimic a cloud infrastructure
- as secure as possible
- as simple as possible for re-gen - use Teraform and Ansible
- pentest it with help from expert colleagues
- the corolarly of crAPI, which is an API full of holes to test against

## Configs

### Install LXD
``
sudo snap install lxd
sudo lxd init
lxc launch ubuntu:24.04 node1 --vm -c limits.cpu=2 -c limits.memory=4GB
lxc launch ubuntu:24.04 node2 --vm -c limits.cpu=2 -c limits.memory=4GB
lxc launch ubuntu:24.04 node3 --vm -c limits.cpu=2 -c limits.memory=4GB
``

### Ubuntu 24.04 adding my local ethernet interface and LXD to a bridge
- https://grok.com/share/c2hhcmQtMg%3D%3D_cd4ce28d-7494-4537-8e09-58da97076d9c
- https://grok.com/share/c2hhcmQtMg%3D%3D_bae421d9-4a6f-4cb0-9401-489ce6c4064d
- https://grok.com/chat/7c37c122-6af9-454c-9ead-4f61568c221a

### Build a 3 node k8s cluster from the LXC nodes
### help me instal kubernetes on my system. I have a linux server with 3 LXD nodes running on it which I want to use for the cluster.
- https://grok.com/share/c2hhcmQtMg%3D%3D_d46857cf-6db0-467c-afee-a30d8a81b83d

### Build the edge services infrastructure
- add a MetalLB load balancer to serve the ingress
- add an Nginx Ingress controller to route the apps
- https://grok.com/share/c2hhcmQtMg%3D%3D_ab0ba4e3-176b-4e96-a5a4-63ab1c70ed42

### Useful
- Enable IP forwarding and bridge settings
- And check kernel modules are there
``
sudo modprobe overlay
sudo modprobe br_netfilter
echo -e "overlay\nbr_netfilter" | sudo tee -a /etc/modules
lsmod | grep -e overlay -e br_netfilter
cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf
net.bridge.bridge-nf-call-iptables  = 1
net.bridge.bridge-nf-call-ip6tables = 1
net.ipv4.ip_forward                 = 1
EOF
sudo sysctl --system
``

### kubectl from the Host
``
curl -LO https://dl.k8s.io/release/v1.29.0/bin/linux/amd64/kubectl
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client
mkdir -p $HOME/.kube
lxc file pull node1/etc/kubernetes/admin.conf $HOME/.kube/config
chown $(id -u):$(id -g) $HOME/.kube/config
``




## Config
https://grok.com/share/c2hhcmQtMg%3D%3D_d46857cf-6db0-467c-afee-a30d8a81b83d

## ERRORS
During init
W0415 12:10:39.169325    3057 checks.go:835] detected that the sandbox image "registry.k8s.io/pause:3.8" of the container runtime is inconsistent with that used by kubeadm. It is recommended that using "registry.k8s.io/pause:3.9" as the CRI sandbox image.

## Post install
our Kubernetes control-plane has initialized successfully!

To start using your cluster, you need to run the following as a regular user:

  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

Alternatively, if you are the root user, you can run:

  export KUBECONFIG=/etc/kubernetes/admin.conf

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

Then you can join any number of worker nodes by running the following on each as root:

kubeadm join 10.167.250.220:6443 --token dukmcs.9s8qma0tg7pw11md \
	--discovery-token-ca-cert-hash sha256:80cb60beaefb6fb78d49c28d72d0c317c2c595d72bc709a3d46c5382c8da5ddc 
r

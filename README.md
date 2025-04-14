To start using your cluster, you need to run the following as a regular user:

  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

Alternatively, if you are the root user, you can run:

  export KUBECONFIG=/etc/kubernetes/admin.conf

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

You can now join any number of control-plane nodes by copying certificate authorities
and service account keys on each node and then running the following as root:

  kubeadm join 10.71.198.184:6443 --token syh7j4.879ywf9pyo57t99x \
	--discovery-token-ca-cert-hash sha256:f44556a4f5fa83a8fffe933217acaffd9fdeaa95a5005401f8e8bb0c867a31ec \
	--control-plane 

Then you can join any number of worker nodes by running the following on each as root:

kubeadm join 10.71.198.184:6443 --token syh7j4.879ywf9pyo57t99x \
	--discovery-token-ca-cert-hash sha256:f44556a4f5fa83a8fffe933217acaffd9fdeaa95a5005401f8e8bb0c867a31ec 
root@node1:~# 

# kates-install
kubeadm join 10.71.198.27:6443 --token yxzgbf.ey9xtrlojeqqoebk \
        --discovery-token-ca-cert-hash sha256:ffc0f3f4e4f88801a5ba52da5dd830e5334474660c27e0e58b23142bf1551fd4 

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

kubeadm join 10.71.198.27:6443 --token yxzgbf.ey9xtrlojeqqoebk \
        --discovery-token-ca-cert-hash sha256:ffc0f3f4e4f88801a5ba52da5dd830e5334474660c27e0e58b23142bf1551fd4 


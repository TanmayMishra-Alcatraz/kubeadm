# kubeadm
After running the bootstrap_kubeadm.sh script on all 3 nodes perform these steps on Control Plane:-


1. sudo kubeadm init --pod-network-cidr=192.168.0.0/16 --cri-socket=unix:///run/containerd/containerd.sock

2. mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config


3. kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml


and after running the kubeadm init command you will get a kubeadm join token paste that on all your worker nodes to join them. Must use sudo.

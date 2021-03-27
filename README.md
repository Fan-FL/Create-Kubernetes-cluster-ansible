# How to create Kubernetes cluster
Refer to https://www.digitalocean.com/community/tutorials/how-to-create-a-kubernetes-cluster-using-kubeadm-on-ubuntu-18-04

**require 2 CPUs.**

**disable the swap in the machine. sudo swapoff -a**

**[WARNING IsDockerSystemdCheck]: detected "cgroupfs" as the Docker cgroup driver. The recommended driver is "systemd". Please follow the guide at http**
Solution: edit /usr/lib/systemd/system/docker.service:
    ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock --exec-opt native.cgroupdriver=systemd
    systemctl daemon-reload
    systemctl restart docker

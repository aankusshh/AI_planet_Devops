### Update Ubuntu packages install required package for this lab
'''
$ sudo apt-get update -y
$ sudo apt-get install apt-transport-https curl conntrack
'''

### Install Docker
'''bash
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
$ ls -l /var/run/docker.sock
$ id
$ sudo usermod -aG docker $USER && newgrp docker
$ id
$ docker --version
'''

### Install Kubectl
'''bash
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl &&   chmod +x ./kubectl && sudo mv ./kubectl /usr/local/bin/kubectl

$ sudo chmod +x /usr/local/bin/kubectl
$ ls -l /usr/local/bin/kubectl
$ kubectl version --short
'''

### Install Minikube
'''bash
$ curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ ls -l 
$ sudo install minikube-linux-amd64 /usr/local/bin/minikube
$ minikube version
'''

### Start Minikube
'''bash
$ kubectl cluster-info
$ minikube start

$ kubectl cluster-info
'''

Check Minikube status
'''bash
$ minikube status
$ kubectl get nodes
'''

# MINIKUBE-INSTALLATION

### Minikube is a tool that enables you to run Kubernetes locally on your computer. It sets up a single-node Kubernetes cluster on a virtual machine (VM) in your local environment, allowing you to develop and test Kubernetes applications without needing a full-scale cluster

how to install Minikube on Rocky Linux 9 step by step ?
To begin its installation, make sure following system requirements are met
● Minimal Install Rocky Linux 9 
● 2GBfreeRAMormore 
● 2CPUsormore
● 25GBfreedisk space 
● Local user with sudo admin rights 
● Internet connectivity 
● Dockeror virtual machine manager like VirtualBox, KVM,and VMware etc

# Enable The Docker Repository
sudo dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo

sudo dnf repolist

![Alt text](https://github.com/NimishRathi/MINIKUBE-INSTALLATION/blob/main/Screenshot%202024-05-18%20002648.png)


# Install Docker CE (Community Edition)
sudo dnf install docker-ce docker-ce-cli containerd.io -y

![Alt text](https://github.com/NimishRathi/MINIKUBE-INSTALLATION/blob/main/Screenshot%202024-05-18%20002801.png)

 ### Add your local user to docker group so that it can run docker commands without sudo
 sudo usermod-aG docker $USER
 newgrp docker

 ![Alt text](https://github.com/NimishRathi/MINIKUBE-INSTALLATION/blob/main/Screenshot%202024-05-18%20002953.png)
 ### Start the docker service run
 sudo systemctl start docker
 sudo systemctl enable docker
 ### To verify the docker installation, run following docker container
 docker run hello-world

### Download and Install Minikube and kubectl

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

The command downloads the latest Minikube binary for Linux (AMD64 architecture) from the specified Google Cloud Storage URL.

sudo install minikube-linux-amd64 /usr/local/bin/minikube 

install the Minikube binary into a system-wide directory, making it executable from any location in the terminal

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

sudo cp kubectl /usr/local/bin/ && sudo chmod +x /usr/local/bin/kubectl

This command copies the kubectl binary to the /usr/local/bin directory. The sudo command is used to execute the cp command with superuser privileges, since copying files to /usr/local/bin typically requires elevated permissions.

# Start the minikube cluster
To start the minikube cluster with docker as driver, run

minikube start --driver docker

![Alt Text](https://github.com/NimishRathi/MINIKUBE-INSTALLATION/blob/main/Screenshot%202024-05-18%20004456.png)

 Execute the following set of commands to view minikube status, Kubernetes cluster and node info,
 minikube status
 
 kubectl cluster-info
 
 kubectl get nodes
 
 ![Alt Text](https://github.com/NimishRathi/MINIKUBE-INSTALLATION/blob/main/Screenshot%202024-05-18%20004516.png)
 
 ![Alt Text](https://github.com/NimishRathi/MINIKUBE-INSTALLATION/blob/main/Screenshot%202024-05-18%20004540.png)
 

 ### done 










 











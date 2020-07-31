#1、installkubelet kubeadm kubectl in foreign  
apt-get update && apt-get install -y apt-transport-https curl                  **（update and doanload tools）**  
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -   **(add public key and load apt-key.gpg )**  
cat <<EOF >/etc/apt/sources.list.d/kubernetes.list                              **(add kubernetes source)**  
deb https://apt.kubernetes.io/ kubernetes-xenial main  
EOF  
apt-get update                                                                   **(update source again)**  
apt-get install -y kubelet kubeadm kubectl                                       **(install lastest kubelet kubeadm kubectl)**  
apt-mark hold kubelet kubeadm kubectl                                            **(setting are not updated with system updates)**  

#2、install kubelet kubeadm kubectl in domestic  
apt-get update && apt-get install -y apt-transport-https curl  
(use apt-key.gpg in tool floler )  
apt-key add apt-key.gpg  
cat <<EOF >/etc/apt/sources.list.d/kubernetes.list  
deb http://mirrors.ustc.edu.cn/kubernetes/apt kubernetes-xenial main  
EOF  
apt-get update  
apt-get install -y kubelet kubeadm kubectl  
apt-mark hold kubelet kubeadm kubectl  

*note:*  
*Check the version of kubelet kubeadm kubectl, command:apt-cache madison  kubeadm kubelet kubectl*  
*install specified version, command:apt-get install -y kubelet=1.15.1-00 kubeadm=1.15.1-00 kubectl=1.15.1-00*  


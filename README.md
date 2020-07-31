# 一、installkubelet kubeadm kubectl in foreign  
## 1、apt-get update && apt-get install -y apt-transport-https curl                  **（update and doanload tools）**  
## 2、curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -   **(add public key and load apt-key.gpg )**  
## 3、cat <<EOF >/etc/apt/sources.list.d/kubernetes.list                              **(add kubernetes source)**  
## 4、deb https://apt.kubernetes.io/ kubernetes-xenial main  
## 5、EOF  
## 6、apt-get update                                                                   **(update source again)**  
## 7、apt-get install -y kubelet kubeadm kubectl                                       **(install lastest kubelet kubeadm kubectl)**  
## 8、apt-mark hold kubelet kubeadm kubectl                                            **(setting are not updated with system updates)**  

# 二、install kubelet kubeadm kubectl in domestic  
## 1、apt-get update && apt-get install -y apt-transport-https curl  
## 2、(use apt-key.gpg in tool floler )  
## 3、apt-key add apt-key.gpg  
## 4、cat <<EOF >/etc/apt/sources.list.d/kubernetes.list  
## 5、deb http://mirrors.ustc.edu.cn/kubernetes/apt kubernetes-xenial main  
## 6、EOF  
## 7、apt-get update  
## 8、apt-get install -y kubelet kubeadm kubectl  
## 9、apt-mark hold kubelet kubeadm kubectl  

### *note:*  
### *Check the version of kubelet kubeadm kubectl, command:apt-cache madison  kubeadm kubelet kubectl*  
### *install specified version, command:apt-get install -y kubelet=1.15.1-00 kubeadm=1.15.1-00 kubectl=1.15.1-00*  


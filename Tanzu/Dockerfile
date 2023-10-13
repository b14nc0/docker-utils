FROM ubuntu:latest
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y curl wget zip vim git gpg ca-certificates
WORKDIR /tmp
#Instalas Tanzu
RUN curl -fsSL https://packages.vmware.com/tools/keys/VMWARE-PACKAGING-GPG-RSA-KEY.pub |  gpg --dearmor -o /etc/apt/keyrings/tanzu-archive-keyring.gpg
RUN echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/tanzu-archive-keyring.gpg] https://storage.googleapis.com/tanzu-cli-os-packages/apt tanzu-cli-jessie main" |  tee /etc/apt/sources.list.d/tanzu.list
RUN apt-get update && apt-get install -y tanzu-cli 

#Instala kubectl
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
RUN chmod +x kubectl
RUN mv kubectl /bin/kubectl
#Instala Helm
RUN curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 && chmod 700 get_helm.sh
RUN ./get_helm.sh
WORKDIR /root
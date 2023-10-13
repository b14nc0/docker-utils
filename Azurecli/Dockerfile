FROM ubuntu:latest
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install -y curl wget zip vim git gnupg software-properties-common
WORKDIR /tmp
#Instalas azureCli
RUN curl -sL https://aka.ms/InstallAzureCLIDeb | bash

#Instala kubectl y kubelogin
RUN az aks install-cli
RUN echo 'alias k=/usr/local/bin/kubectl' >> ~/.bashrc

#Instala Helm
RUN curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 && chmod 700 get_helm.sh
RUN ./get_helm.sh

#Instalar terraform
RUN wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
RUN echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | tee /etc/apt/sources.list.d/hashicorp.list
RUN apt update && apt-get install terraform


WORKDIR /root
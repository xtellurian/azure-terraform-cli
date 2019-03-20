# this dockerfile builds the image used as a CLI
ARG AZURE_CLI_VERSION

FROM microsoft/azure-cli:${AZURE_CLI_VERSION}

ARG TERRAFORM_VERSION
ARG HELM_VERSION

RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/local/bin/terraform && \
    rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip

RUN az aks install-cli

RUN wget https://storage.googleapis.com/kubernetes-helm/helm-${HELM_VERSION}-linux-amd64.tar.gz && \
    tar -zxvf helm-${HELM_VERSION}-linux-amd64.tar.gz && \
    mv linux-amd64/helm /usr/local/bin/helm && \
    rm helm-${HELM_VERSION}-linux-amd64.tar.gz
    
ENV PATH="/terraform:${PATH}"

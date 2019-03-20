# azure-terraform-cli
A docker container with Azure CLI and terraform

## Quickstart

```sh
AZ_VERSION="2.0.49"
TF_VERSION="0.11.10"
HELM_VERSION="v2.11.0"

cd docker
docker build -t az-tf-cli --build-arg AZURE_CLI_VERSION=$AZ_VERSION --build-arg TERRAFORM_VERSION=$TF_VERSION --build-arg HELM_VERSION=$HELM_VERSION .

docker run -it az-tf-cli 

$ bash-4.4~ terraform -v
Terraform v0.11.10

```

## What's in the box?

A docker container that you can run interactively with the following tools installed:

 * Azure CLI
 * Terraform CLI
 * kubectl
 * Helm

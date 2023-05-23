# Container-Orchestration-with-Kubernetes

## Project 1: Deploy MongoDB and Mongo Express into local K8s cluster

## Technologies used:
Kubernetes, Docker, MongoDB, Mongo Express

## Project Description:
Setup local K8s cluster with Minikube
Deploy MongoDB and MongoExpress with configuration and credentials extracted into ConfigMap and Secret

## Notes:
- To create an external address for accessing the application in the browser - `minikube service mongo-express-service` 

![image 1](https://github.com/rachana-uniyal/Container-Orchestration-with-Kubernetes/blob/main/images/1.png)

![image 2](https://github.com/rachana-uniyal/Container-Orchestration-with-Kubernetes/blob/main/images/2.png)


## Project 2: Deploy Mosquitto message broker with ConfigMap and Secret Volume Types

### Technologies used

- Kubernetes
- Docker
- Mosquitto

### Project Description

Define configuration and passwords for Mosquitto message broker with ConfigMap and Secret Volume types

## Project 3: Install a stateful service (MongoDB) on Kubernetes using Helm

### Technologies used

- K8s
- Helm
- MongoDB
- Mongo Express
- Linode LKE
- Linux

### Project Description

Create a managed K8s cluster with Linode Kubernetes Engine

Deploy replicated MongoDB service in LKE cluster using a Helm chart

Configure data persistence for MongoDB with Linode’s cloud storage

Deploy UI client Mongo Express for MongoDB

Deploy and configure nginx ingress to access the UI application from the browser

## Notes

1. Add helm repo - 'helm repo add mongodb [https://mongodb.github.io/helm-charts](https://mongodb.github.io/helm-charts)'

2. Install MongoDB using chart - 'helm install MongoDB --values test-mongodb.yaml bitnami/mongodb'

3. Deploy Mongo Express - 'kubectl apply -f test-mongo-express.yaml'


## Project 4: Deploy our web application in K8s cluster from private Docker registry

### Technologies used

- Kubernetes
- Helm
- AWS ECR
- Docker

### Project Description

Create Secret for credentials for the private Docker registry

Configure the Docker registry secret in the application Deployment component

Deploy web application image from our private Docker registry in K8s cluster

### Notes


##### login in docker private repo

    docker login -u username -p password 

##### generated file
    cat .docker/config.json
    cat .docker/config.json | base64

##### create docker login secret from config.json file

    kubectl create secret generic my-registry-key \
    --from-file=.dockerconfigjson=.docker/config.json \
    --type=kubernetes.io/dockerconfigjson

    kubectl create secret generic my-registry-key --from-file=.dockerconfigjson=.docker/config.json --type=kubernetes.io/dockerconfigjson

    kubect get secret

##### create docker login secret with login credentials

    kubectl create secret docker-registry my-registry-key \
    --docker-server=https://private-repo \
    --docker-username=user \
    --docker-password=pwd

    kubectl create secret docker-registry my-registry-key --docker-server=https://private-repo --docker-username=user --docker-password=pwd

##### access minikube console

    minikube ssh

##### copy config.json file from Minikube to my host

    scp -i $(minikube ssh-key) docker@$(minikube ip):.docker/config.json .docker/config.json









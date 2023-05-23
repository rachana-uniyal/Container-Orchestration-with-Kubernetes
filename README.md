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



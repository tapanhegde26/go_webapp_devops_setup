# go_webapp_devops_setup
Sample go application(web) is containerized, deployed in k8s cluster in cloud with helm charts

## Build and run application in local
```
go build -o main
./main
```
## Docker build and run
```
docker build -t tapan2609/go-web-app:v1 .
docker run -p 8080:8080 tapan2609/go-web-app:v1
```
## create EKS cluster
```
eksctl create cluster --name demo-cluster --region us-east-1
```
## Deploy k8s objects
```
cd k8s/manifests/
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
```
## Install Ingress controller
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.11.1/deploy/static/provider/aws/deploy.yaml
```

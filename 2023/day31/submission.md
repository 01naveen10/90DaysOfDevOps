
## Task-01:

## Install minikube on your local
A) download uding choco ==> choco install minikube
    minikube start --driver=docker
    also install kubernetes cli kubectl

## Task-02:

## Create your first pod on Kubernetes through minikube.

We are suggesting you make an nginx pod, but you can always show your creativity and do it on your own.
A)
minikube start
kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.10
kubectl expose deployment hello-minikube --type=NodePort --port=8080
kubectl get pod
minikube service hello-minikube --url
kubectl delete services hello-minikube
kubectl delete deployment hello-minikube
////////////////////////////////////////////////
create folder 
create service.yaml and deployment.yaml

service.yaml////////////
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
  labels:
    env: sandbox
spec:
  type: LoadBalancer
  ports:
  - port: 80
  selector:
    env: sandbox

deployment.yaml///////////
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    env: sandbox
spec:
  replicas: 3
  selector:
    matchLabels:
      env: sandbox
  template:
    metadata:
      labels:
        env: sandbox
    spec:
      containers:
      - name: nginx
        image: nginx
        ports:
        - containerPort: 80

commands:
minikube start
kubectl create -f service.yaml
kubectl create -f deployment.yaml
Kubectl get pods
minikube service nginx-service
minikube delete --all
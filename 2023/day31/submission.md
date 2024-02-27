
## Task-01:

## Install minikube on your local
A) download uding choco ==> choco install minikube
    minikube start --driver=docker
    also install kubernetes cli kubectl

    //for ubuntu ec2 instance
    Need to visit https://minikube.sigs.k8s.io/docs/start/
    curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    sudo install minikube-linux-amd64 /usr/local/bin/minikube
    Install docker
    docker system prune
    minikube delete
    minikube start --driver=docker
    sudo usermod -aG docker $USER && newgrp docker
    kubectl get po -A
    sudo snap install kubectl
    sudo snap install kubectl --classic
    kubectl get po -A
    minikube status
    kubectl get node
    https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04

## Task-02:

## Create your first pod on Kubernetes through minikube.

We are suggesting you make an nginx pod, but you can always show your creativity and do it on your own.
A)

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


///////////////////////////////////////////////////////
git clone project
run it in local then build docke rfile and run then push it to dockerhub

create pod.yaml file//////////////////
apiVersion: v1
kind: Pod
metadata:
  name: simple-nodejs-website
spec:
  containers:
  - name: simple-nodejs-website
    image: 01naveen10/simple-nodejs-website:latest
    ports:
    - containerPort: 3000
///////////////////////////////////////
minikube start
kubectl apply -f pod.yaml
kubectl get pods -o wide
minikube ssh
curl -L http://10.244.0.4:3000
exit
kubectl delete pod simple-nodejs-website


if we delete th epod it is gone then we cna't say it is production ready so we use deployment and we represent the content with labels and selector and replicas fo rauto scaling and load balancing so that it can handle even if pods are crashed it will one more again
create deploy.yaml//////////////////
apiVersion: apps/v1
kind: Deployment
metadata:
  name: simple-nodejs
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: simple-nodejs-website
        image: 01naveen10/simple-nodejs-website:latest
        ports:
        - containerPort: 3000
kubectl apply -f deploy.yaml
kubectl get pods -o wide
minikube ssh
curl -L http://10.244.0.7:3000
exit
kubectl delete -f deploy.yaml --to delete all pods


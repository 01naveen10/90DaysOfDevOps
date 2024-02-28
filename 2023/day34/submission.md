## Task-1:

- Create a Service for your todo-app Deployment from Day-32
- Create a Service definition for your todo-app Deployment in a YAML file.
- Apply the Service definition to your K8s (minikube) cluster using the `kubectl apply -f service.yml -n <namespace-name>` command.
- Verify that the Service is working by accessing the todo-app using the Service's IP and Port in your Namespace.

A)
If the application wants to access other pod then if it is deleted due to resource issue or other then the ip address will be changed and it will be gone, to sole this we use services which allocate ip for the cluster to access

service.yaml///////////////
apiVersion: v1
kind: Service
metadata:
  name: simple-nodejs-website-service
spec:
  selector:
    app: simple-nodejs-website
  ports:
    - protocol: TCP
      port: 80
      targetPort: 3000
/////////////////
kubectl apply -f service.yml -n myspac
kubectl get services -n myspac

## Task-2:

- Create a ClusterIP Service for accessing the todo-app from within the cluster
- Create a ClusterIP Service definition for your todo-app Deployment in a YAML file.
- Apply the ClusterIP Service definition to your K8s (minikube) cluster using the `kubectl apply -f cluster-ip-service.yml -n <namespace-name>` command.
- Verify that the ClusterIP Service is working by accessing the todo-app from another Pod in the cluster in your Namespace.

A) 

cluster-service.yaml///////////////
apiVersion: v1
kind: Service
metadata:
  name: simple-nodejs-cluster-service
spec:
  selector:
    app: simple-nodejs-website
  ports:
    - protocol: TCP
      port: 80
      targetPort: 3000
/////////////////
kubectl apply -f cluster-service.yml -n myspac
kubectl exec -it simple-nodejs-website-645b4ccdf8-wdmnz -n myspac -- /bin/sh
/app # wget -qO- http://simple-nodejs-website-service:80 # check the response



NotE:use nodeport to access sit out of minikube cluster
## Task-3:

- Create a LoadBalancer Service for accessing the todo-app from outside the cluster
- Create a LoadBalancer Service definition for your todo-app Deployment in a YAML file.
- Apply the LoadBalancer Service definition to your K8s (minikube) cluster using the `kubectl apply -f load-balancer-service.yml -n <namespace-name>` command.
- Verify that the LoadBalancer Service is working by accessing the todo-app from outside the cluster in your Namespace.

A)
lb-service.yaml
apiVersion: v1
kind: Service
metadata:
  name: nodejs-app-loadbalancer
  labels:
    app: simple-nodjes-website
spec:
  type: LoadBalancer
  selector:
    app: simple-nodejs-website
  ports:
    - protocol: TCP
      port: 80
      targetPort: 3000

apply it 
kubectl apply -f lb-service.yaml  -n myspac

to check the cluster ip and external ip to access
kubectl get svc -n mysapc

kubectl delete svc nodejs-app-loadBalancer -n myspac
kubectl delete svc simple-nodejs-website-service -n myspac

to delete deployments
kubectl get deployments -n myspace
kubectl delete deployment simple-nodejs-website -n myspac

to delete pod
kubectl delete pods <pod-name> -n myspace


to get all the pods detials in all the namespaces
kubectl get pods --all-namespaces # for pods
kubectl get deployments --all-namespaces  # for dpeloyments



kubectl apply -f lb-service.yaml  -n myspac

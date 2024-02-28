# Today's task:

## Task 1:

- Create a Namespace for your Deployment

- Use the command `kubectl create namespace <namespace-name>` to create a Namespace

- Update the deployment.yml file to include the Namespace

- Apply the updated deployment using the command:
  `kubectl apply -f deployment.yml -n <namespace-name>`

- Verify that the Namespace has been created by checking the status of the Namespaces in your cluster.
A) default namespaces that are present
kube-system      - containers sytem processors, master node kubectl processes etc (shouldn't change them)
kube-public      - publicly accessible data, configmaps which contian cluster information
kube-node-lease  - availability of nodes
default          - resources are created here

1. resources grouped for namespaces
2. many teams, same application
3. resource sharing - to different clusters
4. access and resource limits to namespaces

you can use 
kubectl apply -f deploy.yaml --namespace myspace
kubectl create namespace myspace
and  add it in deployment file
/////
apiVersion
kind
metadata
    name
    namespace: myspace

kubectl get pods --namespace myspace
done






## Task 2:

- Read about Services, Load Balancing, and Networking in Kubernetes. Refer official documentation of kubernetes [Link](https://kubernetes.io/docs/concepts/services-networking/)
A)
Pods contain ip address inside cluster
The Service API lets you expose an application running in Pods to be reachable from outside your cluster.

pod has its own cluster wide ip address which can help in load balancing

networking implementation:
pods can communicate with all other pods on any other node without NAT
agents on a node (e.g. system daemons, kubelet) can communicate with all pods on that node
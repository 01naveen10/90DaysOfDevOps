## Tasks

1. What is Kubernetes? Write in your own words and why do we call it k8s?
A) Kubernetes is open source container orchestration tool used to manage containers and deploy them by automating it using master and node architecture. K and and 8 characters till S is called k 8's and used to tell that it is written in spoken language

2. What are the benefits of using k8s?
A) scalability, high availability, portability, efficiency and automation

3. Explain the architecture of Kubernetes, refer to [this video](https://youtu.be/FqfoDUhzyDo)
A) master node which contains api server, etcd, scheduler, control manager
node where the applications usually run it contains kubelets to manage them, kube proxy for load balancing

4. What is Control Plane?
a) it contols all the nodes using kubectl .it contains control manager, scheduler, etcd and api servers which are used to connect the nodes to master node. 

5. Write the difference between kubectl and kubelets.
A) kubectl is cli tool used to manage deploy clusters. to view manage logs , resources and manage them
kubelet takes commands from master node and performs the tasks and monitors the nodes

6. Explain the role of the API server.
A) exposes kubernetesapi to allow users to connect and interact with it. it monitors , validates clusters
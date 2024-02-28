1.What is Kubernetes and why it is important?
A)
kubernetes is container orchaestration platform used to manage deploy containers. It helps in auto scaling, autohealing and loadbalacing

2.What is difference between docker swarm and kubernetes?
A)
docker swarm is docker native whereas kubernetes is open source it has larger community and useful of rmore complex structures

3.How does Kubernetes handle network communication between containers?
A)
it provides networking model which assigns each pod unique ip address so they can communicate wit each othe rin acluster and other pods outside it provides network overlay

4.How does Kubernetes handle scaling of applications?
A)
It has built in support for horizontal and vertical scaling. It scales depending on the meory usage, cpu etc

5.What is a Kubernetes Deployment and how does it differ from a ReplicaSet?
A)
It maintians the number of pods that need ot be run it provides features as scaling, roll back and updates

6.Can you explain the concept of rolling updates in Kubernetes?
A)
allowing update gradually and terminating th eold poda and sending traffic to the new pods gradually

7.How does Kubernetes handle network security and access control?
A) 
Network polices, Service Accounts, Role based access contorl rbac, autorization

8.Can you give an example of how Kubernetes can be used to deploy a highly available application?
A) 
create multiple replicas and deployment for health check and replacement
load balancer and ingress for traffic and high availability

9.What is namespace is kubernetes? Which namespace any pod takes if we don't specify any namespace?
A)
to provide scope for clusters

10.How ingress helps in kubernetes?
A)
it provides api object for external access

11.Explain different types of services in kubernetes?
A)
clusterIP, NodePort, LoadBalancer, External Name

12.Can you explain the concept of self-healing in Kubernetes and give examples of how it works?
A)
to detect and recover form failues without manual intervention
restarting failed containers, roll back to previous version of application pod

13.How does Kubernetes handle storage management for containers?
A)
PersistentVolume , Persistent Volume Claim
Storage Class
Volume Plugins

14.How does the NodePort service work?
A)
it exposes local cluster to outside form port range 30k to 32k

15.What is a multinode cluster and single-node cluster in Kubernetes?
A)
multinode cluster contian multiple node like kubelet kubeproxy and container runtime whereas single node contains only one node making it suitable for testing deploying small scale applications

16.Difference between create and apply in kubernetes?
A) create will create new resource based on yaml file whereas update cna create and update
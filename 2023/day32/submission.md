## Task-1:

**Create one Deployment file to deploy a sample todo-app on K8s using "Auto-healing" and "Auto-Scaling" feature**

- add a deployment.yml file (sample is kept in the folder for your reference)
- apply the deployment to your k8s (minikube) cluster by command
  `kubectl apply -f deployment.yml`

A) copy thr git repo of nodjes website i created created dockerfile fo rit build image and test run then docker push

create deployment file for it (google it change ports and name) (../day31/submission.md)
create service.yaml file for it//////////////////
apiVersion: v1
kind: Service
metadata:
  name: simple-nodejs-service
spec:
  type: NodePort
  selector:
    app: simple-nodejs-website
  ports:
    - port: 80
      targetPort: 3000
      nodePort: 30007

kubectl apply -f service.yaml
kubectl get svc /to get serivce details and ip of ip address inside cluster
minikube service simple-nodejs-service --url //http://192.168.49.2:30007
give ip for it by going 
sudo vim /etc/hosts ==>add ip address (192.168.49.2 simple-nodejs-website.com)

## Today's task:

## Task 1:

- Create a ConfigMap for your Deployment
- Create a ConfigMap for your Deployment using a file or the command line
- Update the deployment.yml file to include the ConfigMap
- Apply the updated deployment using the command: `kubectl apply -f deployment.yml -n <namespace-name>`
- Verify that the ConfigMap has been created by checking the status of the ConfigMaps in your Namespace.

A)
kubectl get configmap --namespace myspac
create file add key value pair to add as source to create ConfigMap

sampleconfile/////////
database.username=admin
database.password=secretpassword
server.port=8080
/////////////////////
## usingfile
kubectl create configmap my-config --from-file=confile -n myspac 
## using commandline
kubectl create configmap my-config --from-literal=database.username=admin --from-literal=database.password=secretpassword --from-literal=server.port=8080 -n myspac

apply updated deployment 
deploy.yaml///////////
apiVersion: apps/v1
kind: Deployment
metadata:
  name: simple-nodejs-website
  namespace: myspac
  labels:
    app: simple-nodejs-website
spec:
  replicas: 2
  selector:
    matchLabels:
      app: simple-nodejs-website
  template:
    metadata:
      labels:
        app: simple-nodejs-website
    spec:
      containers:
      - name: simple-nodejs-website
        image: 01naveen10/simple-nodejs-website:latest
        ports:
        - containerPort: 3000
        volumeMounts:                # Add this section
        - name: config-volume         # Volume name
          mountPath: /config          # Mount path in the container
      volumes:                       # Add this section
      - name: config-volume          # Volume name
        configMap:
          name: my-config            # Name of the ConfigMap
//////////

kubectl get configmaps -n myspac



## Task 2:

- Create a Secret for your Deployment
- Create a Secret for your Deployment using a file or the command line
- Update the deployment.yml file to include the Secret
- Apply the updated deployment using the command: `kubectl apply -f deployment.yml -n <namespace-name>`
- Verify that the Secret has been created by checking the status of the Secrets in your Namespace.

A)
## using file
create secret file and create secret in kubernetes 
secret.txt --> this is a secret idiot you can't read
kubectl create secret generic my-secret --from-file=my_secret.txt -n myspac
## using command line
kubectl create secret generic my-secret -from-literal=password=1234 -n myspac

update deployment
kind: Deployment
metadata:
  name: simple-nodejs-website
  namespace: myspac
  labels:
    app: simple-nodejs-website
spec:
  replicas: 2
  selector:
    matchLabels:
      app: simple-nodejs-website
  template:
    metadata:
      labels:
        app: simple-nodejs-website
    spec:
      containers:
      - name: simple-nodejs-website
        image: 01naveen10/simple-nodejs-website:latest
        ports:
        - containerPort: 3000
        volumeMounts:
        - name: config-volume
          mountPath: /config
        - name: secret-volume
          mountPath: /secrets
      volumes:
      - name: config-volume
        configMap:
          name: my-config
      - name: secret-volume
        secret:
          secretName: my-secret
///////////////////////////////////
kubectl apply -f deploy.yaml -n myspac
 kubectl get secrets -n myspac

to check 
 kubectl exec -it simple-nodejs-website-7446876bdf-2hhtp -n myspac -- /bin/sh
cd / ==> secrets ==> my_secret.txt
cd / ==> config ==> confile

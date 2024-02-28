## Today's tasks:

### Task 1:

Add a Persistent Volume to your Deployment todo app.

- Create a Persistent Volume using a file on your node. [Template](https://github.com/LondheShubham153/90DaysOfDevOps/blob/94e3970819e097a5b8edea40fe565d583419f912/2023/day36/pv.yml)

- Create a Persistent Volume Claim that references the Persistent Volume. [Template](https://github.com/LondheShubham153/90DaysOfDevOps/blob/94e3970819e097a5b8edea40fe565d583419f912/2023/day36/pvc.yml)

- Update your deployment.yml file to include the Persistent Volume Claim. After Applying pv.yml pvc.yml your deployment file look like this [Template](https://github.com/LondheShubham153/90DaysOfDevOps/blob/94e3970819e097a5b8edea40fe565d583419f912/2023/day36/Deployment.yml)

- Apply the updated deployment using the command: `kubectl apply -f deployment.yml`

- Verify that the Persistent Volume has been added to your Deployment by checking the status of the Pods and Persistent Volumes in your cluster. Use this commands `kubectl get pods` , `kubectl get pv`

⚠️ Don't forget: To apply changes or create files in your Kubernetes deployments, each file must be applied separately. ⚠️

my_pv.yaml/////////////////////////////
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-node-app
spec:
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Retain
  hostPath:
    path: "/tmp/data"
///////////////////////////////////////

kubectl apply -f my_pv.yaml -n myspac

my_pv_claim.yaml///////////////////////
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-node-app
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 500Mi
///////////////////////////////////////

kubectl apply -f my_pv_claim.yaml -n myspac

update deploy/yaml //////////////////////
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
        volumeMounts:
        - name: config-volume
          mountPath: /config
        - name: secret-volume
          mountPath: /secrets
        - name: node-app-data
          mountPath: /app
      volumes:
      - name: config-volume
        configMap:
          name: my-config
      - name: secret-volume
        secret:
          secretName: my-secret
      - name: node-app-data
        persistentVolumeClaim:
          claimName: pvc-node-app
/////////////////////////////////////////

 kubectl apply -f deploy.yaml -n myspac

kubectl get pv -n myspac


### Task 2:

Accessing data in the Persistent Volume,

- Connect to a Pod in your Deployment using command : `kubectl exec -it <pod-name> -- /bin/bash
- Verify that you can access the data stored in the Persistent Volume from within the Pod

 kubectl exec -it simple-nodejs-website-7446876bdf-2hhtp -n myspac -- /bin/sh

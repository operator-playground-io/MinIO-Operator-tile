---
title: MinIO Instance Creation tutorial
description: This tutorial explains how create Instances for your MinIO Operator.
---

### Create MinIO Instance and Sevice to access MinIO Server

Execute below command to create a secret with proper access-key and secret-key:

```execute
kubectl create secret generic minio-creds-secret --from-literal=accesskey=admin --from-literal=secretkey=secret@123456 --namespace my-minio-operator
```

Output:

```
secret/minio-creds-secret created
```

### Create below yaml file to create MinIO Operator Instance

```execute
cat <<'EOF' > MinioInstance.yaml
apiVersion: miniocontroller.min.io/v1beta1
kind: MinIOInstance
metadata:
  name: minio
spec:
  replicas: 4
  credsSecret:
    name: minio-creds-secret
  requestAutoCert: false
EOF
```

Execute below command to create MinIO Operator instance:

```execute
kubectl create -f MinioInstance.yaml -n my-minio-operator
```

You will see the following output:

```
minioinstance.miniocontroller.min.io/minio created
```

Check the Pods status:

```execute
kubectl get pods -n my-minio-operator
```

You will see similar to this output:

```
NAME                              READY   STATUS    RESTARTS   AGE
minio-0                           1/1     Running   0          115s
minio-1                           1/1     Running   0          115s
minio-2                           1/1     Running   0          115s
minio-3                           1/1     Running   0          115s
minio-operator-6cccf9f587-72xcp   1/1     Running   0          17m
```

Check all the kubernetes resources:

```execute
kubectl get all -n my-minio-operator
```


You will see similar to this output:

```
NAME                                  READY   STATUS    RESTARTS   AGE
pod/minio-0                           1/1     Running   0          2m8s
pod/minio-1                           1/1     Running   0          2m8s
pod/minio-2                           1/1     Running   0          2m8s
pod/minio-3                           1/1     Running   0          2m8s
pod/minio-operator-6cccf9f587-72xcp   1/1     Running   0          17m

NAME                   TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)    AGE
service/minio-hl-svc   ClusterIP   None         <none>        9000/TCP   2m8s

NAME                             READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/minio-operator   1/1     1            1           17m

NAME                                        DESIRED   CURRENT   READY   AGE
replicaset.apps/minio-operator-6cccf9f587   1         1         1       17m

NAME                     READY   AGE
statefulset.apps/minio   4/4     2m8s

```

### Create NodePort Service to access MinIO's Pod 

```execute
cat <<'EOF' > MinioNodePortService.yaml
apiVersion: v1
kind: Service
metadata:
  name: minio-service
spec:
  type: NodePort
  ports:
  - port: 9000
    nodePort: 30205
  selector:
    v1beta1.min.io/instance: minio
EOF
```

Execute below command to create NodePort Service

```execute
kubectl create -f MinioNodePortService.yaml -n my-minio-operator
```

Output:

```
service/minio-service created
```

### Access MinIO's dashboard

Execute below command to get the NodePort service:

```execute
kubectl get svc -n my-minio-operator
```

Output will be similar to below output:

```
NAME            TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
minio-hl-svc    ClusterIP   None            <none>        9000/TCP         84m
minio-service   NodePort    10.107.138.82   <none>        9000:30205/TCP   81m
```

The Port value for "minio-service" of Type NodePort is : 30205

We will use this port to access MinIO's Pod using below URL: 

Click on http://##DNS.ip##:30205 to access MinIO's dashboard from your browser.

You will see the MinIO's Login page as below :


 ![](_images/login-console.PNG)





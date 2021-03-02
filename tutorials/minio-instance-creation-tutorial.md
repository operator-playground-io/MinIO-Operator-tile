---
title: MinIO Instance Creation
description: Learn how to create an instance of your MinIO Operator.
---



### Create the Secret with proper access-key and secret-key

-  Execute the command below to create a secret with proper access-key and secret-key.

```execute
kubectl create secret generic minio-creds-secret --from-literal=accesskey=admin --from-literal=secretkey=secret@123456 --namespace my-minio-operator
```

The output should follow like this.

```
secret/minio-creds-secret created
```

### Create MinIO Instance

**Step 1: Create the below yaml definition of the Custom Resource.**   

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

**Step 2: Execute the command below to create MinIO Operator instance.**

```execute
kubectl create -f MinioInstance.yaml -n my-minio-operator
```

You will see the following output:

```
minioinstance.miniocontroller.min.io/minio created
```

**Step 3: Check the Pods status.**

```execute
kubectl get pods -n my-minio-operator
```

This should produce the below details.

```
NAME                              READY   STATUS    RESTARTS   AGE
minio-0                           1/1     Running   0          115s
minio-1                           1/1     Running   0          115s
minio-2                           1/1     Running   0          115s
minio-3                           1/1     Running   0          115s
minio-operator-6cccf9f587-72xcp   1/1     Running   0          17m
```

**Step 4:  Check all the Kubernetes resources.**

```execute
kubectl get all -n my-minio-operator
```


The following output gets displayed.

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

### Create NodePort Service to access MinIO Server Pod 

**Step 1: Create the below yaml definition of the Custom Resource to create `NodePort` Service.**   

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

**Step 2: Execute below command to create NodePort Service.**

```execute
kubectl create -f MinioNodePortService.yaml -n my-minio-operator
```

This should produce the following output.

```
service/minio-service created
```

### Access MinIO's dashboard

Step 1: Execute the command below to get the NodePort service.

```execute
kubectl get svc -n my-minio-operator
```

You should see the below output.

```
NAME            TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
minio-hl-svc    ClusterIP   None            <none>        9000/TCP         84m
minio-service   NodePort    10.107.138.82   <none>        9000:30205/TCP   81m
```

Here, the port number for "minio-service" of Type NodePort is 30205.

Step 2: Click on the link below to access MinIO dashboard from your browser.

http://##DNS.ip##:30205

This will redirect you to the Login Page as shown below.

 ![](_images/login-console.PNG)


### Conclusion

We are able to access MinIO's dashboard.

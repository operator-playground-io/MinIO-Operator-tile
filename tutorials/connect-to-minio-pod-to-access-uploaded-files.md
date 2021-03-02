---
title: Connect to the MinIO's Pod and access file uploaded in bucket.
description: Learn how to connect to the MinIO Pod and access files from bucket.
---


### Connect to MinIO's Pod and access files uploaded into MinIO Storage Bucket


**Step 1: Execute the following below command to list out MinIO's pods inside namespace "my-minio-operator"**

```execute
kubectl get pods -n my-minio-operator
```

You will see a similar output as below:

```
NAME                              READY   STATUS    RESTARTS   AGE
minio-0                           1/1     Running   0          115s
minio-1                           1/1     Running   0          115s
minio-2                           1/1     Running   0          115s
minio-3                           1/1     Running   0          115s
minio-operator-6cccf9f587-72xcp   1/1     Running   0          17m
```

**Step 2: Connect to the MinIO's pod.**

 - Add the MinIO's podname in the below command and copy it to the terminal to execute.
 
 ```copycommand
 kubectl exec -it <podname> -n my-minio-operator -- sh
 ``` 

**Step 3: Execute the following command to check uploaded file inside "test" bucket which reside on containers volume mountpath: "/export".**

```execute
cd /export/test
ls
```

You will see a similar output as below:

```
index.html
```

The same uploaded data file can be accessed by other applications deployed on the same cluster.


**Step 4: Exit from the Operator pod.**

```execute
exit
```

You’re done!

### Conclusion

You are able to connect to the MinIO's Pod and access file uploaded in bucket.


---
title: MinIO Operator Installation Verification
description: Learn how to verify that the Grafana Operator has been properly installed in the namespace.
---

### Check the MinIO Operator

**Step 1: Verify that the MinIO Operator has been installed successfully by executing below command.**


```execute
kubectl get csv -n my-minio-operator
```

You will see a similar output as below.

```output
NAME                      DISPLAY            VERSION   REPLACES                  PHASE
minio-operator.v3.2.0   MinIO Operator   3.2.0     minio-operator.v3.0.2   Succeeded
```

Please wait for the PHASE status to be "Succeeded", then proceed.

**Step 2: Check the pod status.**

```execute
kubectl get pods -n my-minio-operator
```

You will see a similar output as below.

```
NAME                                READY   STATUS    RESTARTS   AGE
minio-operator-7574bbdbc9-skdk8   1/1     Running   0          45s
```

From above, you can see the pod details as follows:
a.	NAME starting with ‘minio-operator' 
b.	READY value is '1/1' 
c.	STATUS is `Running

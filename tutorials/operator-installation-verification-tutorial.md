---
title: MinIO Operator Installation Verification Tutorial
description: This tutorial explains how to verify that the MinIO Operator installed properly in the namespace
---

### Check the MinIO Operator

After installation, verify that operator is installed successfully by executing the below command.

```execute
kubectl get csv -n my-minio-operator
```

You should see a similar output as below.

```output
NAME                      DISPLAY            VERSION   REPLACES                  PHASE
minio-operator.v3.2.0   MinIO Operator   3.2.0     minio-operator.v3.0.2   Succeeded
```

**Please wait till `PHASE` status will be `Succeeded` and then proceed further.**

After the installation is successful , you can check your operator's pod by executing the below command.

```execute
kubectl get pods -n my-minio-operator
```

You should see a pod starting with 'minio-operator' with Ready value '1/1' and Status 'Running' like the output as below.

```output
NAME                                READY   STATUS    RESTARTS   AGE
minio-operator-7574bbdbc9-skdk8   1/1     Running   0          45s
```


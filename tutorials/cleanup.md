---
title: MinIO Operator cleanup Tutorial
description: This tutorial explains how to cleanup Operator
---


### Cleaning Up Operator



***Delete the operator's CRs by kubectl delete commands :***

Example:
 
 ```copycommand
 kubectl delete -f MinioInstance.yaml -n my-minio-operator
 ```

Note: Here MinioInstance.yaml  is the CR of the MinIO Server Instance.

Similarly,delete all the CRs.
 

***Delete the operator by kubectl delete command:***
 
 
 Example:
 
 ```copycommand
 kubectl delete -f https://operatorhub.io/install/minio-operator.yaml
 ```
 

 
***Delete all the yaml files:***
 
 Example:
 
  ```copycommand
  rm -rf MinioInstance.yaml
  ```
  
  Similarly, you can delete rest of yaml files.


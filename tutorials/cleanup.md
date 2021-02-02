---
title: MinIO Operator cleanup Tutorial
description: This tutorial explains how to cleanup Operator
---


### Cleaning Up Operator



***Delete the operator's custom resource by kubectl delete commands :***

Example:
 
 ```execute
 kubectl delete -f MinioInstance.yaml -n my-minio-operator
 ```

Note: Here MinioInstance.yaml is the custom resource of the MinIO Server Instance.



***Delete the operator by kubectl delete command:***
 
 
 Example:
 
 ```execute
 kubectl delete -f https://operatorhub.io/install/minio-operator.yaml
 ```
 

 
***Delete all the yaml files:***
 
 Example:
 
  ```execute
  rm -rf MinioInstance.yaml
  rm -rf MinioNodePortService.yaml
  ```
  
 


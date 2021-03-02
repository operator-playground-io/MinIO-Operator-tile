---
title: MinIO Operator clean-up 
description: Learn how to cleanup the MinIO Operator resources.
---


### Cleaning Up MinIO Operator Resources


**Step 1: Delete the operator's Custom Resources by using `kubectl delete` commands as below.**

 
 ```execute
 kubectl delete -f MinioInstance.yaml -n my-minio-operator
 ```

Note: Here MinioInstance.yaml is the custom resource of the MinIO Server Instance.


**Step 2: Delete the operator by using `kubectl delete` command as below.**
 
   
 ```execute
 kubectl delete -f https://operatorhub.io/install/minio-operator.yaml
 ```
 
 
**Step 3: Deleting the CSV resource.**
 
 
  ```execute
  rm -rf MinioInstance.yaml
  rm -rf MinioNodePortService.yaml
  ```
  
 ### Conclusion

You’ve successfully deleted all the MinIO operator resources.

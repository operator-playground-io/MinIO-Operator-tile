<h1 align="center">MinIO Operator</h1>

![Logo](_images/logo.png)

MinIO is a high performance distributed object storage server, designed for large-scale private cloud infrastructure. MinIO is designed in a cloud-native manner to scale sustainably in multi-tenant environments. Orchestration platforms like Kubernetes provide perfect launchpad for MinIO to scale. MinIO is Open Source, Enterprise-Grade, Amazon S3 Compatible Object Storage. 
MinIO-Operator brings native MinIO, MCS, and KES support to Kubernetes. 

### Key features :

- SQL Select
- Encryption & WORM
- Multi-Site Federation
- Lambda Compute
- Integration with IAM Tools
- Erasure Code & Bitrot Protection



### MinIO-Operator currently supports following features:

- Configure the fundamentals of MinIO like versions, persistence, erasure code configuration, and replicas.
- Launch MinIO Clusters with specific affinity, toleration and other pre-defined settings
- Create and delete highly available distributed MinIO clusters
- Automatic TLS: Deploy TLS enabled MinIO clusters with builtin certificate signing requests.
- Expand an existing MinIO cluster	
- Use a custom template for hostname discovery	
- Use PodSecurityPolicy for MinIO Pods	
- Deploy MCS with MinIO cluster	
- Deploy KES with MinIO cluster


### Architecture
The following diagram describes the architecture of a MinIO deployed into Kubernetes:

![](_images/minio-on-kubernetes.PNG)


### Objective of tutorial

In this tutorial,we are going to cover following topics:

1. Install MinIO Operator and verify its successful installation.
2. Create MinIO Instance and verify status of pods and services.
3. Access MinIO Console and create storage bucket and upload files.
4. Connect to the pods and access files stored inside storage bucket.
5. Cleanup Operator.








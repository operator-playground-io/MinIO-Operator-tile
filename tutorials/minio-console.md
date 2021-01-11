---
title: Access MinIO Console
description: This tutorial explains how to access minios console.
---

### Access MinIO's Console 


- To login into MinIO's console click on below URL :

http://##DNS.ip##:30205 


You will see the MinIO's Login page as below :

![](_images/login-console.PNG)

- Login to the console using access key and secret key as below :

 access key: admin
 secret key: secret@123456

![](_images/login-creds.PNG)

 Note: above accesskey and secretkey we have used while creating secret.


- Once logged-in, you will see MinIO's console as below:


![](_images/logged-in-console.PNG)



The MinIO Console provides a graphical user interface (GUI) for interacting with MinIO Tenants.
Administrators of MinIO Tenants can perform a variety of tasks through the Console, including user creation, policy configuration, and bucket replication. 


### Create Storage Bucket 

Step 1: To create Storage Bucket, click on red coloured "+" icon on right side below corner.

![](_images/console-option.png)

You will see all the options as below:

![](_images/option.PNG)

Step 2: Click on "Create bucket" option.

![](_images/create-bucket.png)

Step 3: Give a name to the storage bucket and just hit enter. 

![](_images/bucket-name.PNG)

Storage bucket will be created and can be seen on left side of the console as shown in below snapshot:

![](_images/bucket-created.png)

Step 4: Click on the option ":" provided to the bucket as shown in the below snapshot.

![](_images/edit-policy-option.png)

You will see options :"Edit policy" and "Delete" 

![](_images/edit-policy.png)

Step 5: To edit policy of the Bucket, click on "Edit policy"

You will see below option :

![](_images/edit-policy-fields.PNG)

Step 6: Provide the "prefix" of Bucket Policy and choose policy as "Read Only" or "Write Only" or "Read and Write" and click on "Add" Button.

Your bucket policy will be added.

![](_images/edit-policy-option-read-write.png)

Once bucket policy is added, you can see the "Remove" button on created Bucket Policy using which we can remove the Bucket Policy.

Also a new column of Bucket Policy is also added.

![](_images/remove-bucket-policy.PNG)

Step 7: If you want to delete the bucket, click on "Delete" option as shown in below snapshot:

![](_images/delete-bucket.png)

### Upload Files into storage bucket

Step 8: To Upload files in bucket click on red coloured "+" option on right side below corner.

Step 9: Click on to "Upload file" option as shown in below snapshot.

![](_images/upload-file.png)

"Open" window to select the file will be opened.

Step 10: Select the file you want to upload in the Bucket.Once file is selected and clicked on "Open",you will see "File uploaded Successfully" message.

![](_images/upload-file-successful.png)

Step 11: If you want to delete the uploaded file, you can click on the option shown in below snapshot and click on Delete.

![](_images/delete-uploaded-file.png)










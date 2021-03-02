---
title: Access MinIO Console
description: Learn how to access Minios console.
---

### Access MinIO Console 

MinIO Console provides a graphical user interface (GUI) for interacting with MinIO Tenants. The administrators of MinIO Tenants can perform a variety of tasks through the console, including user creation, policy configuration, and bucket replication.

**Step 1: Use the below URL to log in to MinIO console.** 

http://##DNS.ip##:30205 


You will see the Login page as below.

![](_images/login-console.PNG)

**Step 2: Use the below access key and secret key to login.** 

 access key: admin
 
 secret key: secret@123456

![](_images/login-creds.PNG)

Note: The above access key and secret key have been used while creating secret.


**Step 3: Once logged-in, you will see the MinIO console as below.**


![](_images/logged-in-console.PNG)



### Create Storage Bucket 

**Step 1: To create storage bucket, click on “+” icon highlighted in red.**

![](_images/console-option.png)

You will see all the available options as below:

![](_images/option.PNG)

**Step 2: Click on "Create bucket" option.**

![](_images/create-bucket.png)

**Step 3: Provide a meaningful name to the storage bucket and press Enter.**

![](_images/bucket-name.PNG)

This will create a storage bucket which can be seen on the left side of the console. See below. 

![](_images/bucket-created.png)

**Step 4: Click on the option ":" available for the bucket as shown in the below snapshot.**

![](_images/edit-policy-option.png)

You will see options :"Edit policy" and "Delete"

![](_images/edit-policy.png)

**Step 5: To edit the policy of the bucket, click on "Edit policy". You will see the following option.**


![](_images/edit-policy-fields.PNG)

**Step 6: Provide the "prefix" to the Bucket Policy and choose policy as "Read Only" or "Write Only" or "Read and Write".**


![](_images/edit-policy-option-read-write.png)

**Step 7: Click on "Add" Button.**

Your bucket policy will be added.


Once your bucket policy is added, you can see the "Remove" button on the created policy draft to remove the bucket policy.

![](_images/remove-bucket-policy.PNG)

You will also see a new column of Bucket Policy added.

**Step 8: Click on "Delete" option if you wish to remove the bucket. See below.**

![](_images/delete-bucket.png)

### Upload files into storage bucket

**Step 1: To upload the files in bucket, click on “+” icon highlighted in red.**

**Step 2: Click on to "Upload file" option as shown in the below snapshot.**

![](_images/upload-file.png)

**Step 3: Select the file you want to upload in the Bucket. Once the file is selected after you pressed "Open", you will see a message "File uploaded Successfully".**

**Step 4: If you want to delete the uploaded file, you can click on the option shown in below snapshot and click on Delete.**

![](_images/upload-file-successful.png)

Step 11: If you want to delete the uploaded file, you can click on the option shown in below snapshot and click on Delete.

![](_images/delete-uploaded-file.png)


### Conclusion

This way, you can access the MinIO console, add files and policy, and delete the uploaded files.







🎯AWS PRactical Assessment -Week 1
-
🧩Task 1- Create a least-privilege policy for S3 write and prove it works
-
1. IAM > Created Policy > JSON
2. {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
               "s3:PutObject",
                "s3:GetObject"
            ],
            "Resource": "arn:aws:s3:::intern-assignments-mansi/uploads/*",
            "Condition": {
                "Bool": {
                    "aws:SecureTransport": "true"
                }
            }
        },
        {
            "Effect": "Deny",
            "Action": "s3:DeleteObject",
            "Resource": "arn:aws:s3:::intern-assignments-mansi/uploads/*"

3. Policy name: InternS3UploadPolicy
4. Created IAM user and attach the policy
5. Created S3 bucket : intern-assignments-mansi
6. Tested using CLI
   -
   [root@ip-10-0-6-19 ~]# aws s3 cp sample.txt s3://intern-assignments-mansi/uploads/sample.txt
   upload: ./sample.txt to s3://intern-assignments-mansi/uploads/sample.txt

   [root@ip-10-0-6-19 ~]# aws s3 rm s3://intern-assignments-yourname/uploads/sample.tx
   delete failed: s3://intern-assignments-yourname/uploads/sample.tx An error occurred (NoSuchBucket) when calling the DeleteObject operation: The specified bucket    does not exist
7. Following are the screenshoots:-

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/55e47dc1-6d68-4891-84c4-cd4e74b8408b" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/31ef80f0-5018-4348-8e0f-00333dbb1376" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ec99e0f1-7505-492e-8a4a-00ae852a97c9" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/fbed72c7-74d1-4da7-9d2a-33f832293369" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/90f968d5-a713-4140-b383-fcdac426fce3" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/2a516888-e7df-4c6d-9894-759455ed3031" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/b0e25ff6-2a91-4b3b-9d05-e346105fbe33" />

🧩Task 2- Launch an EC2 and serve a simple web page
-
1. EC2 >Launch instance
   ❖ Name : webserver-1
   ❖ AMI: Amazon Linux 2
   ❖ Public IP: 13.1250.126.121
2. User data:
   
  🟂 #!/bin/bash
   yum update -y
   yum install -y httpd
   systemctl enable httpd
   systemctl start httpd
   HOSTNAME=$(hostname)
   PRIVATE_IP=$(curl -s http://169.254.169.254/latest/meta-data/local-ipv4)
   cat > /var/www/html/index.html <<EOF
   <html><body>
   <h1>Hostname: ${HOSTNAME}</h1>
   <p>Private IP: ${PRIVATE_IP}</p>
   </body></html>
   EOF 
4. Launch and access via browser
5. Following are the screenshoots:-

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/cdef9fed-8299-4a09-b2d1-1c08f0aa4ba0" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/150b3a17-1e1d-4cc0-b2bd-cd996d00f736" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4f950389-b81b-47e2-ab11-3114b03ebd75" />

🧩Task 3- Create, attach, and snapshot an EBS data volume
 -
 1. Creared Volume: 8 GB, same zone from task 1
 2. Attach the volume to instance /dev/xvdbf
 3. sudo mkfs -t ext4 /dev/xvdbf
   , sudo mkdir /data
    ,sudo mount /dev/xvdbf /data
    ,echo "Hare krishna" | sudo tee /data/test.txt
    ,sudo blkid /dev/xvdbf
 4. Add to /etc/fstab using UUID
 5. Created snapshoot from volume
 6. Restored the snapshoot to new volume and attach and verify
 7.    sudo mkdir /mnt/restored
      , sudo mount /dev/xvdbf /mnt/restored
       , cat /mnt/restored/test.txt
 8. vol-089d4cc8a1949824c
    & snap-0e600a510abb9fc59
 9. Following are the screenshoots:-
    
 <img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/6a9f13be-f55f-4d1b-8606-aadbefc77942" />
 
 <img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/aa7876b4-71f6-4cc6-a66f-990919772ff5" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7836de75-c508-4e99-9d92-beb1a466cbe8" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ce4e8bdd-f3dc-460c-b532-f9aab562af09" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/cfec7659-6190-4f8d-85c0-e2d590325d8d" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/adcd80eb-93db-41b9-9996-6f7a29b50fe0" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0124c4e1-1bab-4990-baa2-715bcc61484f" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/5d389d44-ad7e-409a-a6c7-b4ad28e0a40b" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/90253b1a-450d-4cb9-8357-ce0438877196" />
 

🧩Task 4- Create a custom AMI and launch a new instance from it (test EBS 
snapshot too)
-
1. Created AMI from Task2 instance
2. Launch the new Instanve from AMI
3. Verify the browser the site is working proprly
4. Attach volume from snapshoot and verify test.txt
5. ami- 0597936867a2c31c3
6. instance id- 0c787133de99461ca
7. public IP: 18.143.76.203
8. Following are the screenshoots:-

 <img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/e36520c2-d196-47cb-b90c-4d0bc631cf09" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0c89f42b-68a2-4dcb-a1f8-3f74589e708f" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/30624f31-081c-4e69-8021-c7e45ba3e762" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ad80d6cc-7571-4896-bc43-b1c47e37b4e3" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a1ae0765-7994-4ff2-9155-00e9a9ea8e37" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7e525bcd-0c65-4242-aa06-836a3ea35404" />

🧩Task 5- Deploy Web App with ALB and Auto Scaling (Launch Template)
-
1. Created Target Group: tg-web-task5
2. Created Application Load balancer : lb-web-task5
3. Created Launch Tamplated : lt-intern-web
4. user data-
   #!/bin/bash
   ,yum update -y
   ,yum install -y httpd
   ,systemctl enable httpd
   ,systemctl start httpd
   ,HOSTNAME=$(hostname)
   ,PRIVATE_IP=$(curl -s http://169.254.169.254/latest/meta-data/local-ipv4)
   ,cat > /var/www/html/index.html <<EOF
   ,<html>
   ,<body>
    ,  <h1>Instance hostname: ${HOSTNAME}</h1>
    ,<p>Private IP: ${PRIVATE_IP}</p>
    ,</body>
   ,</html>
   ,EOF
   ,chown -R apache:apache /var/www/html
5. Created Auto Sacling Group
6. Validate and tested the sites and insrances
7. DNS- 
   http://lb-web-task5-690576389.ap-southeast-1.elb.amazonaws.com/
8. Following are the screenshoots:-

   
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ce0271f1-bf2d-4cfe-aca0-864cc8fa469a" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0d82a9b7-c188-4c80-bc03-bc50e1dfd769" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/695caea1-132c-4440-abee-3b3b49437e5f" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/3ef56ea4-9ac1-4ede-99e4-d8dee421e986" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/554e55eb-005c-4b1a-9246-a5822a3a2258" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/e85e2dcf-2890-4fe2-9f74-f88f057d1308" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/751b5b9e-8f46-4c43-8062-56153bb09ab4" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/8216b123-2107-47b7-8651-addd0349859a" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4d7872c6-c222-4aa0-a000-576c1ceb10ea" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a3a2e85d-2875-45ac-89ec-2570e3f6ddfb" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/d3cb7397-96e4-4ba2-beb8-01d3adff6f7e" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/36673b7b-2ee1-4902-b949-9d7f962c1309" />

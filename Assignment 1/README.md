🎯AWS PRactical Assessment -Week 1

🧩Task 1- Create a least-privilege policy for S3 write and prove it works

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
   
        }
    ]
}

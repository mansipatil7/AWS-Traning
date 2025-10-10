# 1 — Basic networking: Create two VPCs and peer them
## Task (simple): Create VPC-A (public + private subnets) and VPC-B (private subnet). Peer them so instances in private subnets can talk

1. VPC-A ID: 01e8376f592152e8f
2. VPC-B ID: 07fc73009dc82e469
3. VPC Peering Connection ID: pcx-062fee82ed309239f

#### Here are the Screenshort of Created VPC-A,subnet,igw and routing table

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/1c21184d-4731-4033-87d4-1ae3c718b326" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c3fbe634-89ea-4cdd-87da-7e03c59f2c07" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/063d324d-f7c3-4ddd-a8f1-67282b8db9cf" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/89df8624-5749-49eb-a8a6-13c8688a56bb" />



#### Here are the Screenshort of Created VPC-B,subnet

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c454331d-5299-4333-a946-b5d2d6881e52" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0262a211-fc47-4187-bb16-30de94a2a278" />


#### Here are the Screenshort of Peering connection

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/dcd43d5c-726e-4b63-9899-a041e58557a0" />


#### Here are the Screenshort of Security Group creted 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/1b73b2b4-b495-4f68-8b73-c8cfce463550" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a19af859-f1ff-486b-87a8-05c29ab709cc" />


#### Here are the Screenshort of route table entries showing peering routes 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/bcfda5fb-e4a0-401b-af4f-f1cf50c23a28" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/991c17b9-752d-47e0-b119-c73592383153" />


```python
iPING 10.1.1.50 (10.1.1.50) 56(84) bytes of data.
64 bytes from 10.1.1.50: icmp_seq=1 ttl=64 time=1.23 ms
64 bytes from 10.1.1.50: icmp_seq=2 ttl=64 time=1.15 ms
64 bytes from 10.1.1.50: icmp_seq=3 ttl=64 time=1.18 ms
64 bytes from 10.1.1.50: icmp_seq=4 ttl=64 time=1.21 ms

--- 10.1.1.50 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3005ms
rtt min/avg/max/mdev = 1.150/1.192/1.230/0.030 ms
```

# 2- Create IAM role, EC2 base server, create AMI & snapshot
## Task (simple): Launch one EC2, attach an IAM role, install a small web page, create an AMI from it, and snapshot a second EBS volume

1. IAM Role ARB:- arn:aws:iam::021891603196:role/Ec2-CW-S3-role
2. EC2 Instance ID:- 0daa3b08a5238f5cf
3. AMI ID:- 02802057a228a17d4
4. EBS Volume:- 092d367a2a6334d4b
5. Snapshoot ID:- 0bd575d6bc82502ef


#### Here i have make the IAM role Ploicy

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/1b561759-1bbe-49b2-ae7b-0391e11d2dc5" />


#### Launch the instance 
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/eb09dbde-45c6-4abc-9f9b-bc63f219da11" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/cbe23a57-11c2-4e94-a701-530e01d66f56" />


#### Here i have create the volume and attach the volume to the instance /dev/xvdf
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a5b25ac2-f4aa-4df9-9cae-ccc7fc470b4f" />
#### Mount is there
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/cf494259-d3a6-4ca6-93b6-7c92cf766c06" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4d9aa727-3162-4f44-8d74-901a403fb5d2" />

#### Here i have took the screenshot 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/cbfe7ad4-0ae2-42d0-a7fc-05be5947cbf2" />


#### Make the volume


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/5bf318a1-ee60-4849-b241-cb2c959b5760" />



#### Finally launch the AMI sucessfully

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/edf761ef-f6fe-4398-819a-f56dbd9bc0ea" />

```python
 curl http://localhost
<!DOCTYPE html>
<html>
<head>
    <title>Hello World</title>
</head>
<body>
    <h1>Hello World from Base App Server!</h1>
    <p>Instance ID: </p>
    <p>Availability Zone: </p>
</body>
</html>

```

# 3 — Public app: ALB + Auto Scaling Group (basic) + S3 static asset
## Task (basic-intermediate): Serve the public app via an ALB using an Auto Scaling Group (ASG) with the AMI from Task 2. Host one static image on S3 and reference it from the web page.

1. S3 bucket name: my-t3-bucket-07
2. S3 object URL: https://my-t3-bucket-07.s3.ap-southeast-1.amazonaws.com/New+Text+Document.txt
3. ALB DNS name: my-app-alb-435449307.ap-southeast-1.elb.amazonaws.com
4. Target Group ARN: tg=arn:aws:elasticloadbalancing:ap-southeast-1:021891603196:targetgroup/my-app-
5. ACG name: my-app-asg

#### Crete the S3 bucket and the page is running

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/3fcd7248-7b18-4dc8-931b-a57c012dea07" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/31b96923-09ef-4cb0-a26c-66dfe58d646a" />

#### created the role for EC2 and S3
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c7280f60-589c-4af6-81bb-cfe1e8ef94f6" />
   

#### Create the target group and load balancer

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/1ec3668e-890d-44f0-b811-be30ffe881e0" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/92b3ee9c-9763-458f-94ff-f41bd8efb4c5" />

#### Launch the template and create the autoscaling group

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/bcd5756f-ce51-415b-8e3a-90d596d485aa" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/8009cfc8-41e2-4a70-bd1f-d9a389efa85b" />



#### Instance Launched by template 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/9b6c8b84-5616-46ae-a336-c963838b564f" />


#### Finally my site is runing using ALB DNS

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a16017f2-4699-4c93-8723-6ebc175a27fa" />



# 4 — Private app: RDS (private) + EFS + private EC2
## Task (basic-intermediate): In VPC-B, host a private app that mounts EFS and connects to an RDS database (both private). The private app must be reachable from instances in VPC-A via peering (but not from the public internet). 

1. RDS endpoint: database-1.c3882me4ccst.ap-southeast-1.rds.amazonaws.com
2. EFS ID: fs-097f1a2c0ba917263
3. 

#### Created Subnet group

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ff0d836b-03e1-42e6-9d15-33e4afd1b197" />


#### Created Database

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/89807d7b-b19a-427a-bd0b-ffcbe55ec0a1" />


#### Created the EFS file
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c096fd18-e463-4f3a-9756-4c4b6dc32c52" />

#### Launch one EC2 in VPC-B private subnet (use the base-app-ami) and in userdata mount EFS and connect to RDS

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/44dfc707-db17-4696-b07a-0d14c0250799" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/e41f2af3-0ca6-47a6-ad51-1497d3623d5c" />


# 5 — Monitoring & Auditing (CloudWatch + CloudTrail)
## Task (basic): Enable Cloud watch and create an SNS email alarm. Also, create a tiny CloudWatch dashboard

#### Here i have created VPC

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/16483275-10bc-422f-98ff-570c8e4459bf" />

#### Launch the Instance

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/9180184d-e358-447e-9ae7-093439092d6b" />

#### Create the SNS Topic and Subscribe Through email

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/3ba2a62f-0219-42d4-b8f8-1e224d6f3c9b" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/f30b3f06-55be-455d-b480-9c55a3f1cb1d" />
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/9c54a01f-7bb2-4c48-873d-8ea15f50fa8b" />


#### Created Cloudwatch Matrics and set the CPU Utilization

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c9c2c2b7-b62f-4884-ba5b-0ded36284d20" />


#### Create the Dashboard

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/945ada75-b46c-46be-a15e-1214cc3e6b86" />

#### Create the cloud watch alarm using SNS (email)

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4d6f1f30-7489-4553-8cd4-cf4e8a4d759b" />


#### On instance , for checking the alaram trigger the CPU and given load ,where i have set 50> 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/43a42492-5b12-4afd-acac-ae7064a80e03" />


#### The SNS jas sen alert notification to email


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ed510990-8860-4ce3-8b72-34f9e1bdaf1f" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/b8570e8c-9876-40d6-bf5f-aed8ac166e57" />


#### Here i had check the CloudTrial log

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4971c393-4de9-4404-a264-e8b8f3513ac4" />


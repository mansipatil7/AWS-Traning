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







<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/cf494259-d3a6-4ca6-93b6-7c92cf766c06" />

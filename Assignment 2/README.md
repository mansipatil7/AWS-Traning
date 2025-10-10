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


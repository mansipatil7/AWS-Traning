# 1 Basic setup
### Task :-🚀
Create an RDS MySQL instance (db.t3.micro, Free Tier eligible)
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a5c0d37f-d8fe-4994-a5b0-9015e8db871d" />
#### Here i have launch the instances for RDS

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/bbcdb511-9a49-49b1-88ea-c0b3f0b6afe8" />

#### Created the subnet group

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/d3a30140-6044-489c-b62f-392d462bc563" />

#### Created the RDS name as- database-1

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/24e5d381-4adc-4561-9585-2357bbf4ac62" />

#### Sucessfuly connected to EC2 instance in the same VPC using MYSQL clint.
### Here i understand the networking and connectivity setup ✅

# 2 Backup & Restore
### Task :-
Your RDS instance accidentally had data deleted. 
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/2cf71336-9f98-423a-ad1a-eb8370185602" />

#### So Enable automated backups and set retention for 7 days. 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/f561bf12-e064-4822-80bc-eb9f72de001d" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/6f6104c3-4304-4eb2-85aa-cfbe12edc281" /> 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4cc3b060-68df-4629-963b-ddff173baa9b" />
 
####  Here i modify the after that put some data in mysql after Took a manual snapshot before simulating data deletion. 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7d455fdd-d62c-4345-aa5d-c5f0248c5cf2" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/d1bb82c2-0ae3-44fe-bd83-2e924289fdcd" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/81d28066-c0d1-464e-bf02-59d01f3c946d" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/6ef06d4b-8264-4db1-9ffc-77ebd288bc37" />


#### Restore from snapshot or Point-In-Time Recovery to recover lost data. 
#### 🧠 Goal: Learn data protection and restore process. 
 
# 3 Read Replica for Load Sharing
### Task :-
Create a Read Replica of your primary RDS

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/95a37452-7c25-4483-bc9f-f9a575ad7784" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4ab0e77d-e9cd-4998-a03c-5313e35264d9" />

#### Here i have created the Read Replica 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/e719ce32-8ee5-458f-a3c8-f4e3cea87407" />

#### Replica is creating 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/1ecafe26-9432-4cdb-bdb0-93611a2b349f" />

#### After the replica is craeted here we are **fail** to write the data, because its read replica

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/de601bf5-db68-4f8d-a4aa-43ff6f8d04bb" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/b197764a-4f68-4456-9f78-4c103735df6b" />

#### After the fail, I Promote the replica to a standalone instance to simulate failover. 
#### 🧠 Goal: Understand scaling reads and replication concepts.


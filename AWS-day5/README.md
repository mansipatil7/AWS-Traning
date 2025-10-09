## Task 1-📝

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/45763db4-cede-4cc0-8a35-244a06ae81bf" />
✅Name the s3 bucker tbucker7
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/cb1c5d0b-578a-4930-8757-23f5ad75de2c" />
✅Enable the versioning to keep multiple objects
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a4864719-2c41-4d22-ace3-13c9562967c0" />
✅Bucket is created sucessfully
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/1ef43443-ab2f-4ef7-8991-e02ce4f69cbb" />
✅Setting the bucket policy for access
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/291b1df2-ebe8-47db-ad9b-d7e03b3ca88e" />
✅I have uploaded the one simple file 
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0d42ce6c-cf52-40de-8b68-7b76343e39e6" />
✅And test that file wich is html through using URL
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/42539d4a-baf4-4f7f-ba8e-e8c7e4397e12" />
✅I have added the same file using some chnages in it for testing how versioning work
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/37b71b21-fa7a-45ab-9a34-0b96951e0fc1" />
✅After delet that oversion we can see the current version is there
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/76488f81-587d-4a42-a1c6-acc65a062896" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0d9b2b60-4cf5-49cd-9b53-2710257cbec1" />
🚀End of the task we are having html file again✅Task 4 is under task 1
 
## Task 3-📝
Here i will suggest Don’t put S3 behind an ALB. Use S3 + CloudFront (CDN) for static hosting. ALB is intended for HTTP(S) load balancing to compute targets (EC2/ECS/Lambda) — ALB cannot natively target an S3 bucket as a target group. If someone suggests “S3 behind ALB”, that usually means running an application layer proxy (EC2) that serves S3 — not recommended.


A. S3 static website + CloudFront CDN (recommended)

How: Put static assets in S3 (private). Create CloudFront distribution with S3 as the origin. Use Origin Access Control (OAC) or Origin Access Identity (OAI) so only CloudFront can read from S3. Use ACM certificate (in us-east-1) for HTTPS on CloudFront. Configure Route 53 DNS to the CloudFront distribution.

Pros: low latency globally, caching reduces origin costs, TLS termination at CloudFront, WAF & edge protection, cost-effective at scale.

Cons: small additional CloudFront cost, invalidation costs for frequent changes (but can use versioned asset filenames).


B. S3 static website (alone)

How: S3 bucket static website hosting, public objects or via pre-signed.

Pros: simplest and cheapest for very small audience.

Cons: not great globally, no native HTTPS for the bucket website endpoint (unless fronted by CloudFront), higher latency for remote users.


C. S3 behind ALB (not recommended)

Reality: ALB cannot directly target S3 buckets. You’d need a proxy (EC2/ECS) behind the ALB that fetches from S3 and serves to clients.

Pros: may give you more control if you must run server-side logic.

Cons: extra EC2 cost, adds latency, increases operational overhead, reduces reliability & scalability benefits of S3+CloudFront. Generally, do not do this for static hosting.

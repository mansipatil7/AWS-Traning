Task 1-
📝Launch a new EC2 instance from a public AMI; attach a fresh gp3 data volume, 
partition/format/mount it for app data, take a point-in-time snapshot, and provide secure 
access via both SSH and Session Manager. 

1. EC2-Launch Instance [Amazon Linux 2] with t2.micro
2. Added IAM with SSMmanager policys
3. Launch and attach gp3 data volume
4. Make partition and Mount the volume
5. Created Volume from EC2 and Created the Snapshoot
6. Access it through Key pair
   
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/33f84aab-9dfd-4f43-a2bf-cae4bb625e87" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a2ad03bf-918a-4cfc-8f28-07b0d3d55988" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/8cd3c28f-4ec4-44c1-a666-de34eac2218f" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/dad870f7-e811-4b9f-b893-eb0c36189c4f" />

Task 2-
📝Create a simple golden AMI from a configured instance (web/app baseline), then launch 
a new instance from that AMI and verify the service comes up without any additional 
manual steps.

1. From Instance created Golden AMI with all required web/app services
2. Verify its working
3. Launch the Instace from that Golden AMI
4. Verify that server is working mannualy and starts automatically

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/bc04e560-a032-4241-9079-829f06811a64" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a02e2192-f31f-4b0e-92cb-123ac62ae0d6" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/d97e0670-5877-4568-a277-128953a4337a" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/27955cf2-d6dc-4abe-b0dc-0c469cfa47e9" />

   

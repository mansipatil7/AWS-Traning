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


Task 3-
📝Migrate application data off the root disk to a separate attached EBS volume, snapshot 
that data volume, replace the original instance, and restore the data by attaching the 
volume to the new instance. 


1. Attached the new EBS Volume to running instance
2. Created Snapshoot of that data volume
3. Terminated the original Instance
4. Launch the new Instance and Verify it working and volume
   

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/26e5f346-2a88-45e7-952a-239b5d772fe3" />


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/49c75dc3-487a-447e-9c4d-a88b9928e00c" />


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a510c505-6bd0-47da-b988-2e0ccbb90e3a" />


Task 4-
📝Restore an EBS snapshot to a new volume in a different Availability Zone, validate data 
integrity there, then copy the same snapshot to another Region, restore it, and verify 
cross‑region recovery.


1. Restore the EBS Snapshoot tp Volume in different AZ
2. Volume is attached to different Instance
3. Validate the data intergrity in  that zone
4. Copy the same snapshoot  to other region and restore it
5. Verify it


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/9c84ff4f-c683-4b9d-b89e-ae77ef09ffb4" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/2898a1b5-8720-41ec-8084-9752f54d95d6" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/e1a4322d-d145-49dc-97ff-9aac170a108c" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ac1cc42c-2cc9-4272-a73c-820b6bfe25d1" />


Task 5-
📝Modify an EBS volume in place (size and/or type), expand the filesystem online, and 
confirm capacity and performance changes without downtime. 


1. Modify the EBS volume size and type
2. expand the file system
3. Confirm capacity and performance changes without down time


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/5bb96419-2c54-47b6-9050-2f97e0196943" />


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/2bb4ecc1-5195-4592-a53f-26228294f00b" />


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/3c8fd07d-ee73-4495-a398-7c0a1bfcdc8e" />


Task 6-
📝Create an AMI backup of a running instance, terminate the original, and relaunch a 
replacement from the AMI to confirm a clean, predictable rebuild. 

1. Terminated the original instance
2. Launch the new instance from the AMI
3. Verify the new instance Launched Clearly


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/435c9ef6-3d75-4d82-b0b6-9211d4dda48d" />


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/82a515c3-7f4f-4795-aefe-959b5ecc19cd" />


<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/cc44bdfc-b2b3-420c-98e1-36732de665a3" />


Task 7-
📝Create a snapshot of a data volume, restore a new volume from that snapshot, attach it 
to an instance, and validate that all expected files are present. 

1. Ceated the snapshoot of data volume
2. Restore new volume from that snapshoot and attach it
3. Check the chnages didi in first volume should preset (files) in preset instance

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0cf78ad4-b754-4284-8814-2513a9d27ca0" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/bd262fa6-b358-45ed-8cd8-d63fda7b5717" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ebe142c3-28e2-4d23-ae56-433f7a7216b2" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/518547c6-5cf3-459a-94b8-04de59b5e70e" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/35f69079-840c-42ed-9675-e84503b6ff4b" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a1c1db02-44a5-44aa-83ce-64cf47e9a615" />

<img width="1635" height="899" alt="Image" src="https://github.com/user-attachments/assets/107c8664-0699-42d7-b245-9447e4132219" />


Task 8-
📝Demonstrate three restore paths from snapshots: (a) create and attach a data volume 
from a snapshot, (b) register/launch an instance from a root‑volume snapshot via AMI.

📌Task 8 is perform in two differnt task , task (a) is perform in task 6 and (b) is perform in task 1.

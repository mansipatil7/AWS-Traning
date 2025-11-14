# Task1
### Set up Prometheus to monitor system metrics using Node Exporter via Docker Compose.
#### 1. Files Description
### docker-compose.yml
Defines two services:

· Prometheus: Monitoring server on port 9090
· Node Exporter: System metrics collector on port 9100

### prometheus.yml
Configuration file for Prometheus with:

· Global scrape interval: 15 seconds
· Two scrape jobs:
  · prometheus: Monitors itself on localhost:9090
  · node_exporter: Collects system metrics from node_exporter:9100

#### 2.Start Services

```bash
docker-compose up -d
```
#### 3. Verify Services Running

```bash
docker-compose ps
```

#### 4.Expected Output:

```
Name                 Command               State           Ports
-------------------------------------------------------------------
node_exporter   /bin/node_exporter --path ...   Up      0.0.0.0:9100->9100/tcp
prometheus      /bin/prometheus --config.f ...   Up      0.0.0.0:9090->9090/tcp
```

#### 5.Docker-compose runnig 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/834f1cb6-2a55-4509-90ae-051f3ca6fc6e" />

#### 6. server status is up 

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/260c27a9-2118-478d-8675-db586da9b5da" />

#### 7. curl to 9091 and ist working on dashboard

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/b6d2e6ba-f8d9-45ef-bdfe-54a6c0199913" />

#### 8. Docker containers are running

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/e812c873-eca5-406c-ae56-a00d88faa932" />


#### 9. Instance image

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/ed6416ed-8686-46fc-a4a6-b15dfe16eabe" />




















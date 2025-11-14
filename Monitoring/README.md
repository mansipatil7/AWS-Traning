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



# Task 2
### Set up a complete observability stack with Loki for log aggregation, Prometheus for metrics, and Grafana for visualization using Docker Compose.
#### 1. docker-compose.yml
Defines five services:

· Prometheus: Monitoring server (port 9090)
· Node Exporter: System metrics collector (port 9100)
· Loki: Log aggregation system (port 3100)
· Promtail: Log collection agent
· Grafana: Visualization dashboard (port 3000

#### 2. Configuration Files

· prometheus.yml: Prometheus configuration with Loki target
· promtail-config.yml: Log collection from /var/log and Docker containers
· dashboard.yaml: Grafana dashboard provisioning
· observability-dashboard.json: Pre-built dashboard with metrics and logs

#### 3. Services and Ports

Service Port Purpose Access URL
Grafana 3000 Visualization dashboard http://localhost:3000
Prometheus 9090 Metrics server http://localhost:9090
Node Exporter 9100 System metrics http://localhost:9100/metrics
Loki 3100 Log aggregation API http://localhost:3100


#### 4. Start All Services
```
bash
docker-compose up -d
```

#### 5. Verify Services Running
```
bash
docker-compose ps
```

#### 6. Expected Output:
```

Name                 Command               State                    Ports
------------------------------------------------------------------------------------------
grafana        /run.sh                    Up      0.0.0.0:3000->3000/tcp
loki           /usr/bin/loki -config ...  Up      0.0.0.0:3100->3100/tcp
node_exporter  /bin/node_exporter --p ... Up      0.0.0.0:9100->9100/tcp
prometheus     /bin/prometheus --conf ... Up      0.0.0.0:9090->9090/tcp
promtail       /usr/bin/promtail -con ... Up
```

#### 7. Here docker-compose up -d , runs sucessfully

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/f1f9c79a-ad4a-40e6-ad86-814cad0e08e3" />


#### 8. docker containers are runnig
```
docker compose logs prometheous | tail -5

```

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/385fc723-29fe-4724-9b5a-ada987563867" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/32cb9417-d921-4c0a-839c-ff2086d3256a" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/30cdf611-2e10-4f42-83d1-4b8ae39d4a3b" />


#### 9. Instance state

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7dd06689-0a8e-449f-8776-08c4f70b07ba" />


#### 10 .  curl -s http://localhost:9090/targets -A 5 "job"

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7473b052-5a39-42c5-a04b-b7f34bc3c214" />

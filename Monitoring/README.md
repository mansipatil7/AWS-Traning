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

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/99384043-6899-4810-a073-716f4d76405a" />

#### 6. localhost:9090/query and metrics

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/fc32e70e-9ae2-403e-b650-bb02e6589a85" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/285ab99e-1005-42ab-96fb-8eec43da5702" />



#### 7. 9091 working on dashboard

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/1071a9df-47c0-4c47-88f9-ab2cca4013b2" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/72c147ae-25de-44b4-b512-e720c53fe1f2" />
#### 8. docker-compose.yml

```bash
version: '3.8'

services:
  prometheus:
    image: prom/prometheus:latest
    container_name: prometheus
    volumes:
      - ./prometheus.yml:/etc/prometheus/prometheus.yml
    ports:
      - "9090:9090"

  node-exporter:
    image: prom/node-exporter:latest
    container_name: node-exporter
    ports:
      - "9100:9100"

```

#### 9. prometheus.yml

```bash
global:
  scrape_interval: 5s

scrape_configs:
  - job_name: "prometheus"
    static_configs:
      - targets: ["localhost:9090"]

  - job_name: "node-exporter"
    static_configs:
      - targets: ["node-exporter:9100"]

```
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

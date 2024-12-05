
# Prometheus
 launch the server  for Monitoring useing prometheus

Install Prometheus

```
wget https://github.com/prometheus/prometheus/releases/download/v2.53.3/prometheus-2.53.3.linux-amd64.tar.gz
```
unzip the file name " prometheus-2.53.3.linux-amd64.tar.gz"
```
tar -xf prometheus-2.53.3.linux-amd64.tar.gz
```
change the file name to prometheus
```
mv prometheus-2.53.3.linux-amd64 prometheus
```
Chanage the directory
```
cd prometheus
```
Configure in the folder /etc/sytemd/system/prometheus.Service
```
vim /etc/systemd/system/prometheus.service
```
Create systemctl file 
```
[Unit]
Description=prometheus Server

[Service]
ExecStart=/opt/prometheus/prometheus --config.file=/opt/prometheus/prometheus.yml

[Install]
WantedBy=multi-user.target
```

#Node configuration

Install node exporeter in the node server in the the directory /opt/

```
https://github.com/prometheus/node_exporter/releases/download/v1.8.2/node_exporter-1.8.2.linux-amd64.tar.gz
```

configure the system ctl 
```

[Unit]
Description=Node Exporter

[Service]
ExecStart=/opt/node_exporter/node_exporter

[Install]
WantedBy=multi-user.target
```

update the file in the .yml file  with the node private ip address example:
```
- job_name: "node-1"
    static_configs:
      - targets: ["172.31.11.215:9100"]
        labels:
          name: "node-1
```
















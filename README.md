# 🌐 network-telemetry-labs

Scripts and labs to collect, normalize, and visualize network telemetry — including **NetFlow**, **SNMP**, and **Syslog** — using **ELK Stack** and **Grafana**.

This repo helps you build visibility pipelines for network performance, security, and anomaly detection across routers, switches, firewalls, and virtual labs.

## 📌 Purpose

Modern networks demand centralized observability. This repo simulates a telemetry workflow from the device to the dashboard using open tooling:

- NetFlow/IPFIX ➡️ Logstash ➡️ Elasticsearch ➡️ Kibana
- SNMP Metrics ➡️ Prometheus ➡️ Grafana
- Syslog Events ➡️ Logstash ➡️ ELK and/or Grafana Loki

It’s designed for:

- NOC & SOC visibility engineers
- NetEngs learning observability
- Security pros building visibility pipelines
- Homelab and CCNP/DevNet automation learners

## 📁 Folder Overview

| Folder         | Description                                                  |
|----------------|--------------------------------------------------------------|
| `netflow/`      | Flow collector config, ingest pipelines, and pcap samples    |
| `snmp/`         | SNMP exporter configs, Prometheus targets, MIB tools         |
| `syslog/`       | Syslog forwarding configs, sample logs, logstash rules       |
| `elk-stack/`    | Docker-compose stack for Elasticsearch, Logstash, Kibana     |
| `grafana/`      | Prebuilt dashboards for SNMP and Syslog visibility           |
| `docs/`         | Setup guides, deep dives, pipeline logic                     |
| `utils/`        | Simulation tools: mock flow sender, syslog emitter, SNMP ping|

## 🚦 Example Workflows

### 🔢 NetFlow
- Ingest using `nfcapd` or mock sender (flowreplay)
- Ship to Logstash (`netflow.conf`)
- Visualize in Kibana (`netflow-dashboard.ndjson`)

### 📡 SNMP
- Export via `snmp_exporter` + Prometheus
- Visualize metrics in Grafana
- Use `mib-walk.sh` for custom device queries

### 🧾 Syslog
- Devices send logs to `rsyslog`
- Forward to Logstash ➡️ Elasticsearch
- Visualize alerts, system events, login activity

## ⚙️ Requirements

- Docker (for ELK stack)
- Prometheus + Grafana (manual or Docker)
- SNMP-enabled test device or emulator
- Python, Bash for tooling

## 🧠 Ideal Use Cases

- Build your own NOC/SOC telemetry lab
- Learn Logstash + pipeline syntax
- Understand SNMP and NetFlow from source to dashboard
- Practice SIEM and logging integrations

## 🧰 Tools Used

- Logstash
- Elasticsearch
- Kibana
- Grafana
- Prometheus
- SNMP Exporter
- NetFlow tools (flow-tools, nfdump)
- Python / Bash scripts

## 🚧 Roadmap

- [ ] Add InfluxDB + Telegraf support
- [ ] Add Grafana Loki + syslog pipeline
- [ ] Add alerting pipeline examples (thresholds, anomaly rules)
- [ ] Add multi-node ELK deployment for scale testing


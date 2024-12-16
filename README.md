# How-To-Setup-Influxdb-Telegraf-And-Grafana-using-Docker-Compose

This repository contains a fully-configurable DevOps monitoring stack leveraging **Grafana**, **InfluxDB**, and **Telegraf**. Using Docker Compose, this setup provides an efficient way to monitor system metrics, visualize data, and gain actionable insights into your infrastructure.

> [!NOTE]  
> Medium Article => [A Beginner’s Guide to Setting Up Grafana, InfluxDB, and Telegraf Using Docker Compose](https://just-merwan.medium.com/a-beginners-guide-to-setting-up-grafana-influxdb-and-telegraf-using-docker-compose-b6a1a4297ae4)

![image](https://github.com/user-attachments/assets/2e0dc0cd-7a37-48cc-98fe-a922559966f4)


## Features
- **Grafana**: Real-time dashboards with customizable visualizations.
- **InfluxDB**: A high-performance time-series database for storing metrics.
- **Telegraf**: A flexible plugin-driven agent to collect and send metrics.
- **Docker Compose**: Simplified setup and deployment with containerized services.

## Repository Contents
- docker-compose.yml: Defines the services (Grafana, InfluxDB, Telegraf) and their configurations.
- telegraf.conf: Configuration file for Telegraf with input and output plugins.

## Prerequisites
Ensure the following tools are installed on your system:
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Installation

1. **Clone the Repository**  
```bash
git clone https://github.com/your-username/devops-monitoring-stack.git
cd devops-monitoring-stack
```

2. **Edit Configuration (Optional)**
Update the telegraf.conf file if you need to customize the metrics collected or the output settings.

3. **Start the Monitoring Stack**
Run the following command to deploy the services:
```bash
docker-compose up -d
```

4. Access the Services
- Grafana: Open your browser and navigate to http://localhost:3000. Default credentials:
> - Username: admin
> - Password: admin
- InfluxDB: Access via http://localhost:8086.
- Telegraf Logs: View logs to confirm metrics are being sent:
```bash
docker logs telegraf
```

## File Overview
- docker-compose.yml

This file defines the services and their configurations. It includes:

> - InfluxDB: Exposes port 8086 with persistent storage.
> - Telegraf: Configured to collect system metrics and send them to InfluxDB.
> - Grafana: Exposes port 3000 with persistent storage for dashboards.

- telegraf.conf

A customizable configuration file for Telegraf. By default, it collects:

> - CPU, memory, and disk usage.
> - Sends metrics to InfluxDB for storage.

## Stopping the Stack
To stop the monitoring stack, use:

```bash
docker-compose down
```

## Customization
### Changing Credentials
Modify the docker-compose.yml file to set secure usernames and passwords for Grafana and InfluxDB.

### Adding More Metrics
Edit the telegraf.conf file to include additional input plugins for other metrics (e.g., MySQL, Docker, or HTTP endpoints). Refer to the Telegraf Plugin List for options.


> [!NOTE]
> Enjoy monitoring your infrastructure with this simplified setup! 🎉

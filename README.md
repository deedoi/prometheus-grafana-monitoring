# Home Network Monitoring Setup

This project create a monitoring system using Prometheus and Grafana, as well as Node Exporter for system metrics and a Pi-hole exporter for my Raspberry Pi DNS statistics.

## Overview

This setup includes:
- Prometheus: For collecting and storing metrics
- Grafana: For visualizing and dashboarding the collected metrics
- Node Exporter: For collecting detailed macOS metrics exporter
- Pi-hole Exporter: Pi-hole DNS statistics exporter

## Prerequisites

- Docker and Docker Compose installed
- A running Pi-hole instance
- Node Exporter installed on systems you want to monitor (including Mac Mini)

## Configuration Files

1. `docker-compose.yml`: Defines the Docker services for Prometheus, Grafana, Node Exporter, and Pi-hole Exporter.
2. `prometheus.yml`: Configuration file for Prometheus, defining scrape configs for various targets.

## Setup Instructions

1. Clone this repository to your local machine.

2. Update the `docker-compose.yml` file:
   - Set the correct `PIHOLE_HOSTNAME`, `PIHOLE_PORT`, and `PIHOLE_API_TOKEN` for your Pi-hole instance.
   - Adjust the Grafana admin password if needed.

3. Update the `prometheus.yml` file:
   - Ensure the targets for each job are correct, especially the `mac_mini` job.

4. Start the services: 
 ```
docker-compose pull
docker-compose up -d
 ```
 - Monitor the disk usage of the Prometheus data volume and adjust retention settings if needed.

## Additional Notes

- The current setup uses the latest versions of Grafana and Prometheus. Be aware of any breaking changes when updating.
- Customize the Grafana dashboards to suit your specific monitoring needs.
- Consider setting up alerting in Grafana for important metrics.
![Prometheus targets](https://github.com/user-attachments/assets/ef8b91f6-0524-41d3-ad1e-c4dd55cf8eed)

![Node exporter metrics run](https://github.com/user-attachments/assets/5e2b170a-b228-4a02-858b-d2d9c4214f62)

![Grafana login page](https://github.com/user-attachments/assets/c6afdb4f-8451-4e7a-9655-e3328c5f2cb8)

![Pihole Dashboard](https://github.com/user-attachments/assets/96790e15-ec61-4f1d-bf08-def2ae2995a9)

![mac mini dashboard](https://github.com/user-attachments/assets/b3f643bb-b60b-4874-b482-9095e0a7331d)


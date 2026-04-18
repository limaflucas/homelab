# Homelab Project

Welcome to the Homelab project. This repository contains Docker Compose configurations for various self-hosted applications and infrastructure services, organized into logical categories.

## Directory Structure

*   **[Apps: Grafana & Monitoring](./apps/grafana/README.md)**: Observability stack for collecting and visualizing metrics and logs (Grafana, VictoriaMetrics, VictoriaLogs, Alloy).
*   **[Apps: Komodo](./apps/komodo/README.md)**: Server and container management tool (Control Plane & Periphery).
*   **[Apps: Outline](./apps/outline/README.md)**: A modern team knowledge base and wiki (Outline, PostgreSQL, Redis, MinIO).
*   **[Databases: MongoDB](./databases/mongodb/README.md)**: A centralized shared MongoDB database for use by other services.
*   **[Networking: Nginx Proxy Manager](./networking/nginx-proxy-manager/README.md)**: Reverse proxy for managing access and SSL certificates.
*   **[Security: Authelia](./security/authelia/README.md)**: Centralized authentication and Single Sign-On (SSO) provider.
*   **[Security: Vaultwarden](./security/vaultwarden/README.md)**: Self-hosted password manager compatible with Bitwarden clients.

## Getting Started

To deploy a specific service, navigate to its respective directory, follow the setup instructions (like creating secret files or configuring `.env` variables) as detailed in its `README.md`, and run:

```bash
docker compose up -d
```

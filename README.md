# Manufacturing Stack

This repository contains a containerized manufacturing technology stack featuring **Ignition**, **PostgreSQL**, and **Timebase**. Each component is dockerized for easy deployment and management.

## Components

The stack is organized into three main component directories:

### 1. [Ignition](./ignition)
Inductive Automation's Ignition SCADA platform.
- **Gateway**: `http://localhost:8088`
- **HTTPS**: `https://localhost:8043`
- **OPC UA**: `opc.tcp://localhost:62541`
- **Database**: PostgreSQL (via `ignition` DB)

### 2. [PostgreSQL](./postgres)
Central relational database server with pgAdmin management interface.
- **PostgreSQL**: `localhost:5432`
- **pgAdmin**: `http://localhost:5080` (or `5050` depending on configuration)
- **Default Credentials**: Check specific `docker-compose.yml` files.

### 3. [Timebase](./timebase)
High-performance time-series historian and collectors.
- **Historian**: TCP 4511/4512
- **Explorer** (Web UI): `http://localhost:4531`
- **Collectors**:
    - **Simulator**: `localhost:4521`
    - **OPC UA**: `localhost:4523`
    - **MQTT**: `localhost:4525`
    - **Sparkplug B**: `localhost:4527`
- **Pulse**: `localhost:4541`

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

You can run each component independently by navigating to its directory and running Docker Compose.

### Running Ignition
```bash
cd ignition
docker-compose up -d
```

### Running PostgreSQL & pgAdmin
```bash
cd postgres
docker-compose up -d
```

### Running Timebase Stack
```bash
cd timebase
docker-compose up -d
```

## Management & Access Points

| Service | URL / Port | Description |
|---------|------------|-------------|
| **Ignition Gateway** | [http://localhost:8088](http://localhost:8088) | SCADA Web Interface |
| **pgAdmin** | [http://localhost:5080](http://localhost:5080) | PostgreSQL Management |
| **Timebase Explorer** | [http://localhost:4531](http://localhost:4531) | Historian Data Explorer |
| **Ignition OPC UA** | `localhost:62541` | Endpoint for OPC Clients |
| **PostgreSQL** | `localhost:5432` | Standard DB Connection |

## License

See [LICENSE](./LICENSE) file for details.

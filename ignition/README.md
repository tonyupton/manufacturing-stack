# Ignition Docker

A Docker Compose setup for running Inductive Automation's Ignition SCADA platform with PostgreSQL database and pgAdmin management interface.

## Services

### Ignition Gateway
- **Image**: `inductiveautomation/ignition:latest`
- **Ports**: 
  - 8088:8088 (Gateway web interface)
  - 8043:8043 (HTTPS)
  - 8060:8060 (Gateway control)
  - 62541:62541 (OPC UA)
- **Memory**: 4GB max, 512MB initial

### PostgreSQL Database
- **Image**: `postgres:latest`
- **Port**: 5432:5432
- **Database**: `ignition`
- **Credentials**: `postgres:password`

### pgAdmin
- **Image**: `dpage/pgadmin4:latest`
- **Port**: 5050:80
- **Credentials**: `admin@example.com:admin`

## Quick Start

```bash
# Start all services
docker-compose up -d

# Stop all services
docker-compose down
```

## Configuration

- Edit `ignition/docker-compose.yml` to modify environment variables
- All data is persisted in Docker volumes
- Services restart automatically unless stopped manually

## Access Points

- Ignition Gateway: http://localhost:8088
- pgAdmin: http://localhost:5050
- PostgreSQL: localhost:5432
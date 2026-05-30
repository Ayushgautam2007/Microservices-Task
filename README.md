# Microservices Containerization Assessment

## Project Overview

This project demonstrates containerization of Node.js microservices using Docker and Docker Compose.

The application contains the following services:

* User Service
* Product Service
* Order Service
* Gateway Service

Each service runs inside its own Docker container and communicates through a shared Docker network.

---

# Project Structure

```text
Microservices-Task/
│
├── Microservices/
│   ├── user-service/
│   │   └── Dockerfile
│   │
│   ├── product-service/
│   │   └── Dockerfile
│   │
│   ├── order-service/
│   │   └── Dockerfile
│   │
│   └── gateway-service/
│       └── Dockerfile
│
├── docker-compose.yml
└── README.md
```

---

# Prerequisites

The following software must be installed:

* Docker
* Docker Compose
* Git

---

# Setup Instructions

## Step 1: Clone Repository

```bash
git clone <repository-url>
cd Microservices-Task
```

---

## Step 2: Build and Start Containers

```bash
docker compose up --build
```

---

## Step 3: Verify Running Containers

```bash
docker ps
```

All containers should appear in `Up` state.

---

# Services and Ports

| Service         | Port |
| --------------- | ---- |
| User Service    | 3000 |
| Product Service | 3001 |
| Order Service   | 3002 |
| Gateway Service | 3003 |

---

# API Testing

## User Service

### Get Users

```bash
curl http://localhost:3000/users
```

Browser:

```text
http://localhost:3000/users
```

---

## Product Service

### Get Products

```bash
curl http://localhost:3001/products
```

Browser:

```text
http://localhost:3001/products
```

---

## Order Service

### Get Orders

```bash
curl http://localhost:3002/orders
```

Browser:

```text
http://localhost:3002/orders
```

---

## Gateway Service

### Get Users via Gateway

```bash
curl http://localhost:3003/api/users
```

### Get Products via Gateway

```bash
curl http://localhost:3003/api/products
```

### Get Orders via Gateway

```bash
curl http://localhost:3003/api/orders
```

Browser:

```text
http://localhost:3003/api/users
http://localhost:3003/api/products
http://localhost:3003/api/orders
```

---

# Docker Compose Configuration

The application uses Docker Compose for:

* Multi-container orchestration
* Shared networking
* Port mapping
* Service dependency management

---

# Stop Containers

```bash
docker compose down
```

---

# Troubleshooting

## Port Already in Use

Check running containers:

```bash
docker ps
```

Stop containers if necessary:

```bash
docker compose down
```

---

## Container Build Issues

Rebuild containers:

```bash
docker compose up --build
```

---

## Docker Logs

Check service logs:

```bash
docker logs <container-name>
```

Example:

```bash
docker logs user-service
```

---

# Screenshots

Include screenshots of:

1. `docker compose up --build`
2. `docker ps`
3. Successful API responses
4. Running containers

---

# Conclusion

All microservices were successfully containerized using Docker and orchestrated using Docker Compose. The services communicate over a shared Docker network and are accessible through their respective ports.

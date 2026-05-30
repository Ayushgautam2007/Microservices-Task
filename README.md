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


## Step 2: Install Docker and Git in Instance Screenshots

<img width="944" height="419" alt="image" src="https://github.com/user-attachments/assets/12fe0e1c-bad3-4506-8f05-3923cac27911" />

<img width="836" height="248" alt="image" src="https://github.com/user-attachments/assets/fcdc97ff-1f4c-41ad-bcc7-93488edee2c4" />


## Step 2: Build and Start Containers

```bash
docker compose up --build -d
<img width="945" height="326" alt="image" src="https://github.com/user-attachments/assets/05ec49ac-53b9-4c96-818f-4e4a38c1cdde" />


```

---

## Step 3: Verify Running Containers

```bash
docker ps

<img width="946" height="174" alt="image" src="https://github.com/user-attachments/assets/895f3347-f288-4d8a-a0e6-b1b1d32a3189" />

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



# 🛠️ Docker-Based Microservices with Reverse Proxy

## 📌 Project Overview

This project demonstrates a simple microservices architecture using **Docker Compose**, consisting of:

- A **Go-based backend service** (`service1`)
- A **Python-based backend service** (`service2`)
- An **NGINX reverse proxy** to route requests to the appropriate service

Each backend exposes two endpoints: `/ping` and `/hello`, and the reverse proxy directs traffic based on path prefixes:

- `http://localhost:8083/service1/` → forwards to `service1`
- `http://localhost:8083/service2/` → forwards to `service2`



## 📁 Project Structure & File Descriptions

```

Assessment Project/
├── docker-compose.yml           # Defines and manages all service containers
├── service1/
│   ├── Dockerfile               # Builds the Go-based backend service
│   └── main.go                  # Source code for the Go service
├── service2/
│   ├── Dockerfile               # Builds the Python-based backend service
│   ├── main.py                  # Source code for the Python service
│   ├── pyproject.toml           # Python project metadata and dependencies
│   └── uv.lock                  # Lock file for reproducible Python installs
└── nginx/
├── Dockerfile              # Builds the custom NGINX reverse proxy image
└── nginx.conf              # NGINX configuration for path-based routing

````


## ▶️ How to Run the Project

> Make sure Docker and Docker Compose are installed and running on your system.

1. **Navigate to the project root:**
   ```bash
   cd Assessment Project
   ```

2. Start the containers:**

   ```bash
   docker compose up -d
   ```

3. **Test the services:**

   * `http://localhost:8083/service1/ping`
   * `http://localhost:8083/service1/hello`
   * `http://localhost:8083/service2/ping`
   * `http://localhost:8083/service2/hello`

4. **Stop the containers:**

   ```bash
   docker compose down
   ```

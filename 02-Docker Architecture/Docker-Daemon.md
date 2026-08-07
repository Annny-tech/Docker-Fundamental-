# Docker Daemon (`dockerd`)

## 📖 Introduction

While exploring Docker Architecture, I learned that the Docker Client only accepts commands from the user—it doesn't actually perform any Docker operations. This made me wonder which component is responsible for creating containers, building images, and managing Docker resources.

After reading Docker's official documentation and other learning resources, I found that all these tasks are handled by the **Docker Daemon (`dockerd`)**, the core background service of Docker.

---

## 🤔 What is Docker Daemon?

The Docker Daemon (`dockerd`) is a background service that listens for Docker API requests and manages Docker objects such as:

- Images
- Containers
- Networks
- Volumes

It is the component that actually performs Docker operations requested by the Docker Client.

In simple terms, **the Docker Daemon is the execution engine behind every Docker command.**

---

## 🏗️ Responsibilities of Docker Daemon

The Docker Daemon is responsible for:

- Building Docker images
- Creating and starting containers
- Stopping and removing containers
- Managing Docker networks
- Managing Docker volumes
- Pulling images from Docker Registry
- Pushing images to Docker Registry
- Monitoring running containers

---

## ⚙️ How Docker Daemon Works

Whenever a user executes a Docker command, the Docker Daemon processes the request.

### Workflow

1. User enters a Docker command.
2. Docker Client sends the request using the REST API.
3. Docker Daemon receives the request.
4. It performs the requested operation.
5. The result is returned to the Docker Client.

---

## 🔄 Docker Daemon Workflow

```text
User
 │
 ▼
Docker Client
 │
 ▼
REST API
 │
 ▼
Docker Daemon (dockerd)
 │
 ├── Build Images
 ├── Run Containers
 ├── Manage Networks
 ├── Manage Volumes
 └── Communicate with Docker Registry
```

---

## 🌍 Real-World Example

Suppose you execute:

```bash
docker pull ubuntu
```

Here's what happens behind the scenes:

- Docker Client receives the command.
- The request is sent to the Docker Daemon.
- The Daemon contacts Docker Hub.
- The Ubuntu image is downloaded.
- The image is stored locally.
- Docker Client displays the download status.

Similarly, when you run:

```bash
docker run ubuntu
```

The Docker Daemon:

- Checks if the image exists locally.
- Downloads it if necessary.
- Creates a new container.
- Starts the container.
- Reports the result back to the Docker Client.

---

## ⭐ Key Features

- Runs continuously as a background service
- Executes Docker commands received from the client
- Manages Docker images and containers
- Handles Docker networking and storage
- Communicates with Docker Registries
- Supports multiple Docker clients simultaneously

---

## 📊 Docker Daemon at a Glance

| Feature | Description |
|----------|-------------|
| Process Name | `dockerd` |
| Runs As | Background Service |
| Receives Requests From | Docker Client |
| Communication | REST API |
| Main Responsibility | Manage Docker Objects |
| Performs Operations | ✅ Yes |

---

## 💡 What I Learned

- Docker Daemon is the core service that executes Docker operations.
- It listens for requests from the Docker Client.
- It manages images, containers, networks, and volumes.
- It communicates with Docker Registries when pulling or pushing images.
- Every Docker command is ultimately processed by the Docker Daemon.

---

## 🎯 Summary

The Docker Daemon (`dockerd`) is the backbone of Docker. It runs as a background service, listens for API requests from the Docker Client, and performs all Docker-related operations. Whether building images, creating containers, or managing Docker resources, the Docker Daemon is responsible for executing the requested tasks.

---

## 📖 What's Next?

In the next section, I'll learn about **Docker Registry** and understand how Docker stores, shares, and retrieves container images.

➡️ **Next:** `docker-registry.md`
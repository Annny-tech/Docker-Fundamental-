# Docker Client (CLI)

## 📖 Introduction

While learning Docker Architecture, I noticed that every Docker command I executed started with the `docker` keyword. This made me curious about how Docker understands these commands and communicates with the rest of the Docker platform.

After exploring Docker's documentation and various learning resources, I learned that the **Docker Client**, also known as the **Docker CLI (Command Line Interface)**, is the primary way users interact with Docker.

---

## 🤔 What is Docker Client?

The Docker Client is a command-line tool that allows users to communicate with the Docker Engine.

Whenever we execute Docker commands such as:

```bash
docker build
docker run
docker pull
docker push
docker ps
```

the Docker Client sends these requests to the **Docker Daemon**, which performs the requested operation.

In simple words, the Docker Client acts as a bridge between the **user** and the **Docker Engine**.

---

## 🏗️ How Docker Client Works

The Docker Client does not perform Docker operations by itself.

Instead, it follows these steps:

1. The user enters a Docker command.
2. The Docker Client interprets the command.
3. The request is sent to the Docker Daemon through the REST API.
4. The Docker Daemon executes the operation.
5. The result is returned to the Docker Client and displayed to the user.

---

## 🔄 Docker Client Workflow

```
User
 │
 ▼
Docker Command
 │
 ▼
Docker Client (CLI)
 │
 ▼
REST API
 │
 ▼
Docker Daemon
 │
 ▼
Docker Resources
(Images, Containers, Networks, Volumes)
```

---

## ⭐ Common Docker Client Commands

| Command | Description |
|----------|-------------|
| `docker version` | Display Docker version information |
| `docker info` | Show Docker system information |
| `docker images` | List all Docker images |
| `docker ps` | List running containers |
| `docker pull` | Download an image from a registry |
| `docker run` | Create and start a container |
| `docker stop` | Stop a running container |
| `docker rm` | Remove a container |
| `docker build` | Build an image from a Dockerfile |
| `docker push` | Upload an image to a registry |

---

## 🌍 Real-World Example

Suppose you want to run an Nginx container.

You execute:

```bash
docker run nginx
```

The following happens:

- The Docker Client receives the command.
- It sends the request to the Docker Daemon.
- The Daemon checks whether the **Nginx** image exists locally.
- If not, it downloads the image from Docker Hub.
- The Daemon creates and starts the container.
- The Docker Client displays the result on the terminal.

Although you execute only one command, the Docker Client and Docker Daemon work together to complete the task.

---

## 💡 What I Learned

- The Docker Client is the interface used to interact with Docker.
- It accepts Docker commands from the user.
- It communicates with the Docker Daemon through the REST API.
- The Docker Client does not perform operations itself; it only sends requests.
- Almost every Docker operation begins with the Docker Client.

---

## 📊 Docker Client at a Glance

| Feature             | Description                     |
|---------------------|---------------------------------|
| Type                | Command Line Interface (CLI)    |
| Purpose             | Communicates with Docker Engine |
| Communication       | Uses REST API                   |
| Executes Operations | ❌ No                          |
| Sends Requests      | ✅ Yes                         |
| User Interaction    | ✅ Yes                         |

---

## 🎯 Summary

The Docker Client (CLI) is the primary interface for interacting with Docker. It accepts commands from the user and forwards them to the Docker Daemon through the REST API. While it doesn't perform Docker operations itself, it serves as the communication bridge between the user and the Docker Engine.

---

## 📖 What's Next?

In the next section, I'll explore the **Docker Daemon (`dockerd`)** to understand how it processes Docker commands and manages containers, images, networks, and volumes.

➡️ **Next:** `docker-daemon.md`
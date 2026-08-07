# Docker Registry

## 📖 Introduction

While learning Docker, I noticed that commands like `docker pull` and `docker push` interact with an online service. This made me curious about where Docker images are stored and how they can be shared across different systems.

After exploring Docker's official documentation and other learning resources, I learned that **Docker Registry** is a centralized storage system used to store, manage, and distribute Docker images.

---

## 🤔 What is Docker Registry?

A Docker Registry is a repository where Docker images are stored.

It allows developers to:

- Store Docker images
- Share images with others
- Download existing images
- Upload custom images
- Manage different image versions

Whenever you use commands like `docker pull` or `docker push`, Docker communicates with a Docker Registry.

---

## 🏗️ Types of Docker Registries

### 1. Public Registry

A public registry allows anyone to access and download images.

The most popular public registry is **Docker Hub**, which hosts thousands of official and community-created images.

Examples:

- nginx
- ubuntu
- mysql
- redis
- node

---

### 2. Private Registry

A private registry is used to securely store an organization's Docker images.

Only authorized users can access these images.

Private registries are commonly used by companies to protect proprietary applications.

Popular private registries include:

- Docker Hub Private Repositories
- Amazon Elastic Container Registry (ECR)
- Azure Container Registry (ACR)
- Google Artifact Registry (GAR)

---

## ⚙️ How Docker Registry Works

Docker Registry acts as a storage location for Docker images.

### Workflow

1. A developer creates a Docker image.
2. The image is uploaded to a Docker Registry using `docker push`.
3. Another user or server downloads the image using `docker pull`.
4. Docker creates containers from the downloaded image.

---

## 🔄 Docker Registry Workflow

```text
Developer
    │
docker build
    │
    ▼
Docker Image
    │
docker push
    ▼
Docker Registry
(Docker Hub / Private Registry)
    │
docker pull
    ▼
Docker Host
    │
docker run
    ▼
Docker Container
```

---

## ⭐ Common Docker Registry Commands

### Pull an Image

```bash
docker pull nginx
```

Downloads the latest **Nginx** image from Docker Hub.

---

### Push an Image

```bash
docker push username/my-app:1.0
```

Uploads a Docker image to a registry.

---

### Search for Images

```bash
docker search ubuntu
```

Searches Docker Hub for available Ubuntu images.

---

### Login to a Registry

```bash
docker login
```

Authenticates your Docker client with a registry before pushing private images.

---

## 🌍 Real-World Example

Suppose you've developed a Java web application.

1. You create a Docker image for the application.
2. You upload the image to Docker Hub.
3. Your teammates download the same image on their systems.
4. Everyone runs identical containers without worrying about missing dependencies or configuration differences.

This makes collaboration and deployment much easier.

---

## 📊 Docker Hub vs Private Registry

| Feature | Docker Hub | Private Registry |
|----------|------------|------------------|
| Access | Public (by default) | Restricted |
| Usage | Open-source & public images | Organization-specific images |
| Security | Basic | Higher |
| Best For | Learning & sharing | Production & enterprise applications |

---

## 💡 What I Learned

- Docker Registry is a centralized storage system for Docker images.
- Docker Hub is the most widely used public Docker Registry.
- Images are uploaded using `docker push` and downloaded using `docker pull`.
- Organizations often use private registries to securely manage their Docker images.
- Docker Registry makes it easy to share and deploy applications consistently across different environments.

---

## 🎯 Summary

Docker Registry is a repository for storing and sharing Docker images. It enables developers to upload, download, and manage images efficiently, making application deployment faster and more consistent. Whether using Docker Hub or a private registry, Docker Registry plays a vital role in the Docker ecosystem.

---

## 📖 What's Next?

In the next section, I'll learn about the **Docker Workflow** to understand how all Docker components work together—from writing a Dockerfile to running a container.

➡️ **Next:** `workflow.md`
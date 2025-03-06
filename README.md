# Docker Zero to Hero 🚀

## Learn Docker with Hands-on Examples

This repository is designed to help you learn Docker from scratch with practical examples. Contributions are most welcome!

If you found this repo useful, give it a **STAR 🌠**.

📺 **Watch the video tutorials on YouTube:**  
[Docker Zero to Hero Playlist](https://www.youtube.com/watch?v=7JZP345yVjw&list=PLdpzxOOAlwvLjb0vTD9BXLOwwLD_GWCmC)

---

## 📌 Table of Contents
- [What is a Container?](#what-is-a-container)
- [Containers vs Virtual Machines](#containers-vs-virtual-machines)
- [Why Are Containers Lightweight?](#why-are-containers-lightweight)
- [What is Docker?](#what-is-docker)
- [Docker Architecture](#docker-architecture)
- [Docker Lifecycle](#docker-lifecycle)
- [Understanding Docker Terminology](#understanding-docker-terminology)
- [Installing Docker](#installing-docker)
- [Running Your First Docker Container](#running-your-first-docker-container)
- [Building Your First Docker Image](#building-your-first-docker-image)

---

## 🔹 What is a Container?
A container is a lightweight, standalone, and executable software package that includes everything needed to run an application: code, runtime, system tools, libraries, and settings.

Think of a container as a **bundle** of your application, its required dependencies, and the minimal system components needed to run it.


---

## 🔹 Containers vs Virtual Machines

![Docker Architecture](/Containarization%20vs%20Virtualization.png)

| Feature | Containers | Virtual Machines (VMs) |
|---------|-----------|------------------------|
| **Resource Utilization** | Shares host OS kernel, lightweight | Includes full OS, resource-intensive |
| **Portability** | Highly portable across systems | Requires compatible hypervisor |
| **Security** | Less isolated but lightweight | More secure but heavy |
| **Management** | Easy to manage and deploy | Requires full VM lifecycle management |

---

## 🔹 Why Are Containers Lightweight?
Containers share the host OS kernel instead of including a full OS, making them **significantly smaller** than VMs. 

For example:
- **Ubuntu Container Base Image**: ~22 MB
- **Ubuntu VM Image**: ~2.3 GB (100x larger!)

Containers use:
- Host's **file system** (via bind mounts)
- Host's **networking stack**
- **System calls** from the host OS
- **Namespaces & cgroups** for isolation

---

## 🔹 What is Docker?
Docker is a **containerization platform** that allows you to:
- Build container images
- Run containers from images
- Push containers to registries (Docker Hub, Quay.io, etc.)

**In simple words:** Docker is a tool that implements the concept of containerization.

---

## 🔹 Docker Architecture

Docker follows a **client-server** architecture:

![Docker Architecture](/Docker%20Architecture.png)

- **Docker Daemon (dockerd)**: The core service managing images, containers, networks, and volumes.
- **Docker Client (docker CLI)**: The command-line tool for interacting with Docker.
- **Docker Registries**: Stores container images (Docker Hub, private registries).

---

## 🔹 Docker Lifecycle
The main Docker workflow involves:
1. **Build** Docker images → `docker build`
2. **Run** a container from an image → `docker run`
3. **Push** the image to a registry → `docker push`

---

## 🔹 Understanding Docker Terminology
- **Docker Daemon:** Handles API requests and manages objects.
- **Docker Client:** CLI tool for interacting with Docker.
- **Docker Registry:** Stores images (e.g., Docker Hub).
- **Dockerfile:** A script containing instructions to build images.
- **Images:** Read-only templates to create containers.
- **Containers:** Running instances of images.

---

## 🔹 Installing Docker
To install Docker, follow the official documentation: [Docker Installation Guide](https://docs.docker.com/get-docker/)

### Install Docker on Ubuntu (Quick Setup):
```bash
sudo apt update
sudo apt install docker.io -y
```

### Start Docker and Grant Access
Ensure the Docker daemon is running:
```bash
sudo systemctl start docker
sudo systemctl enable docker
```

Grant your user access to run Docker commands without `sudo`:
```bash
sudo usermod -aG docker $USER
```
**(Logout and log back in for changes to take effect.)**

---

## 🔹 Running Your First Docker Container
Verify Docker installation by running:
```bash
docker run hello-world
```

If you get a **permission denied** error:
1. Check if Docker daemon is running:
   ```bash
   sudo systemctl status docker
   ```
2. If it's not running, start it:
   ```bash
   sudo systemctl start docker
   ```

---

## 🔹 Building Your First Docker Image
Clone this repository:
```bash
git clone https://github.com/iam-veeramalla/Docker-Zero-to-Hero
cd Docker-Zero-to-Hero/examples
```

### Login to Docker Hub
```bash
docker login
```

### Build a Docker Image
```bash
docker build -t your-username/my-first-docker-image:latest .
```

### Sample Output
```bash
Sending build context to Docker daemon  992.8kB
Step 1/6 : FROM ubuntu:latest
latest: Pulling from library/ubuntu
...
Hello from Docker!
```

---

🚀 **Now you're ready to dive into the examples and start learning Docker!** Happy learning! 🎉



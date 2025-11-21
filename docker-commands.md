# 🐳 Docker Commands Cheat Sheet

## 🔍 Docker Version & Info
| Command | Description |
|--------|-------------|
| `docker --version` | Show Docker version |
| `docker info` | Show system-wide Docker information |
| `docker help` | Show Docker command help |

---

## 📦 Docker Images
| Command | Description |
|--------|-------------|
| `docker images` | List downloaded images |
| `docker pull <image>` | Download image from Docker Hub |
| `docker rmi <image-id>` | Remove image |
| `docker build -t <name> .` | Build image from Dockerfile |
| `docker tag <image> <repo>/<name>:tag` | Tag an image |
| `docker image prune` | Remove unused images |

---

## 🏃 Docker Containers
| Command | Description |
|--------|-------------|
| `docker ps` | List running containers |
| `docker ps -a` | List all containers |
| `docker run <image>` | Run container |
| `docker run -d <image>` | Run in detached mode |
| `docker run -it <image> /bin/bash` | Run container & open shell |
| `docker stop <container-id>` | Stop container |
| `docker start <container-id>` | Start container |
| `docker restart <container-id>` | Restart container |
| `docker rm <container-id>` | Remove container |
| `docker kill <container-id>` | Force stop container |

---

## 📥 Upload / Download Data
| Command | Description |
|--------|-------------|
| `docker cp <container>:/path file` | Copy from container |
| `docker cp file <container>:/path` | Copy into container |

---

## 📄 Container Logs
| Command | Description |
|--------|-------------|
| `docker logs <container>` | Show container logs |
| `docker logs -f <container>` | Follow real-time logs |
| `docker logs --tail 100 <container>` | Last 100 log lines |

---

## 📊 Stats & Monitoring
| Command | Description |
|--------|-------------|
| `docker stats` | Live resource usage |
| `docker top <container>` | Show processes running in container |
| `docker inspect <container>` | Show details |

---

## 🌐 Docker Networking
| Command | Description |
|--------|-------------|
| `docker network ls` | List networks |
| `docker network create <name>` | Create network |
| `docker network inspect <name>` | Inspect network |
| `docker network rm <name>` | Remove network |

---

## 💾 Docker Volumes
| Command | Description |
|--------|-------------|
| `docker volume ls` | List volumes |
| `docker volume create <name>` | Create volume |
| `docker volume inspect <name>` | Inspect volume |
| `docker volume rm <name>` | Delete volume |

---

## ⚙ Docker Compose
| Command | Description |
|--------|-------------|
| `docker-compose up` | Deploy containers |
| `docker-compose up -d` | Run in detached mode |
| `docker-compose down` | Stop & remove stack |
| `docker-compose ps` | Show compose services |
| `docker-compose logs -f` | Follow logs |
| `docker-compose restart` | Restart services |

---

## 🧽 Clean Up System
| Command | Description |
|--------|-------------|
| `docker system prune` | Remove unused data |
| `docker system df` | Show disk usage |

---

## 🚀 Example Run Command
```bash
docker run -d -p 8080:80 nginx

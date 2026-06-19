# YT-MLOPS-Docker-Masterclass

<img width="1069" height="754" alt="image" src="https://github.com/user-attachments/assets/4fd08636-8afe-4941-8e97-a16037934a59" />

<img width="1343" height="736" alt="image" src="https://github.com/user-attachments/assets/c926e1b1-0684-4ada-8c47-ffed494a5190" />


The 5000 port showen in picture is of image port that we map to our pc or cloud port
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

```bash id="olfsjp"
# Install Docker Desktop
# Provides Docker Engine and a graphical interface for managing containers

# Sign in to Docker Hub
# Authenticate with your Docker Hub account
docker login

# Verify Docker installation
# Check that Docker is installed and working correctly
docker --version

# Test Docker setup
# Download and run a sample container to confirm Docker is working
docker run hello-world

# Build a Docker image
# Create an image from the Dockerfile in the current directory
docker build -t <local-image-name> .

# Run a container
# Start a container from a local image and expose a port
docker run -p <host-port>:<container-port> <local-image-name>

# Tag an image
# Create a Docker Hub tag for the local image
docker tag <local-image-name> <dockerhub-username>/<repository-name>:latest

# Push an image
# Upload the tagged image to Docker Hub
docker push <dockerhub-username>/<repository-name>:latest

# Pull an image
# Download an image from Docker Hub
docker pull <dockerhub-username>/<repository-name>:latest

# Run a pulled image
# Start a container from the downloaded image
docker run -p <host-port>:<container-port> <dockerhub-username>/<repository-name>:latest
```

**Placeholders**

```bash id="xv2r8n"
<local-image-name>   # Name of the image on your machine
<dockerhub-username> # Your Docker Hub username
<repository-name>    # Repository name on Docker Hub
<host-port>          # Port on your computer
<container-port>     # Port exposed by the container
```

**Workflow**

```bash id="g7k3dm"
# Build → Run → Tag → Push → Pull → Run

docker build -t <local-image-name> .
docker run -p <host-port>:<container-port> <local-image-name>

docker tag <local-image-name> <dockerhub-username>/<repository-name>:latest
docker push <dockerhub-username>/<repository-name>:latest

docker pull <dockerhub-username>/<repository-name>:latest
docker run -p <host-port>:<container-port> <dockerhub-username>/<repository-name>:latest
```





<details>
<summary>Click to expand</summary>

```bash
```bash id="r4g8nq"
# docker login
# Prerequisites:
# - Docker Desktop installed and running
# - Docker Hub account created
docker login


# docker --version
# Prerequisites:
# - Docker CLI installed
docker --version


# docker run hello-world
# Prerequisites:
# - Docker Engine running
# - Internet connection (if image is not already downloaded)
docker run hello-world


# docker build -t <local-image-name> .
# Prerequisites:
# - Dockerfile exists in the current directory
# - Application source code is present
# - Required files are not excluded by .dockerignore
docker build -t <local-image-name> .


# docker run -p <host-port>:<container-port> <local-image-name>
# Prerequisites:
# - Image already built locally
# - Application inside the container listens on <container-port>
# - <host-port> is available on the host machine
docker run -p <host-port>:<container-port> <local-image-name>


# docker tag <local-image-name> <dockerhub-username>/<repository-name>:latest
# Prerequisites:
# - Local image exists
# - Docker Hub repository name chosen
docker tag <local-image-name> <dockerhub-username>/<repository-name>:latest


# docker push <dockerhub-username>/<repository-name>:latest
# Prerequisites:
# - Logged in to Docker Hub
# - Image tagged with Docker Hub repository name
# - Permission to push to the repository
docker push <dockerhub-username>/<repository-name>:latest


# docker pull <dockerhub-username>/<repository-name>:latest
# Prerequisites:
# - Internet connection
# - Image exists in Docker Hub repository
# - Access permission (for private repositories)
docker pull <dockerhub-username>/<repository-name>:latest


# docker run -p <host-port>:<container-port> <dockerhub-username>/<repository-name>:latest
# Prerequisites:
# - Image pulled successfully (or accessible from Docker Hub)
# - Application listens on <container-port>
# - <host-port> is available on the host machine
docker run -p <host-port>:<container-port> <dockerhub-username>/<repository-name>:latest
```

### Quick Readiness Checklist

```bash id="8b3mzx"
✓ Docker Desktop installed
✓ Docker Engine running
✓ Docker Hub account created
✓ Dockerfile available
✓ Application source code available
✓ Local image built
✓ Docker Hub repository chosen
✓ Internet connection available
✓ Required ports identified and available
```

### Dependency Flow

```bash id="m7w2kd"
Docker Desktop
    ↓
docker login
    ↓
Dockerfile + Source Code
    ↓
docker build
    ↓
Local Image
    ↓
docker run

Local Image
    ↓
docker tag
    ↓
docker push
    ↓
Docker Hub Repository
    ↓
docker pull
    ↓
docker run
```

...
```

</details>

# 🚀 My Docker Learning Journey

Welcome to my Docker learning repository! 🐳 This repo highlights my self-taught journey through Docker and how I've applied its concepts to real-world projects. Throughout this process, I’ve learned how to create, manage, and deploy containerized applications efficiently.

## 🛠️ Tools & Technologies Used

- **Docker** 🐳: Containerization tool for building, deploying, and running applications.
- **Docker Compose** 📝: A tool for defining and running multi-container Docker applications.
- **Docker Hub** 🔥: A cloud-based registry for sharing Docker images.

## 🌱 Learning Process

### 1. **Understanding Containers** 🏗️
Docker allows you to package your application and its dependencies into a container. This makes it easier to run your app anywhere, without worrying about OS compatibility. Containers are lightweight, fast, and portable, making them a great choice for modern software development.

#### Key Docker Commands:
- `docker build -t <image-name> .` - Build a Docker image from a Dockerfile.
- `docker run -d -p 8080:80 <image-name>` - Run a container in detached mode with port mapping.
- `docker ps` - List all running containers.
- `docker images` - List all Docker images on your system.
- `docker stop <container-id>` - Stop a running container.

### 2. **Working with Docker Images** 🖼️
Docker images are the blueprints for containers. I learned to create custom images, use base images, and optimize them for different environments. Understanding how to build small and efficient images is crucial for faster deployments.

#### Important Notes on Docker Images:
- Docker images are **immutable** once created. Every time you run a container, it’s an exact replica of the image.
- **Layers**: Docker images consist of layers, which are cached to speed up builds. However, the more layers an image has, the bigger it can get, so it’s essential to minimize layers.
  
#### Example of a Dockerfile:
```dockerfile
# Use an official Node.js runtime as a parent image
FROM node:14

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the current directory contents into the container
COPY . .

# Install any needed dependencies
RUN npm install

# Make port 8080 available to the world outside the container
EXPOSE 8080

# Run the app
CMD ["node", "app.js"]

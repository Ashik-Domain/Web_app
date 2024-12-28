# Dockerized Web Application Deployment Using AWS Elastic Beanstalk

This project demonstrates creating a custom Docker image with an Nginx server, running it in a Docker container, and deploying it on AWS Elastic Beanstalk for scalable and efficient web hosting.

## Introduction
This project utilizes **Docker** for containerization and **AWS Elastic Beanstalk (EBS)** for deployment. Elastic Beanstalk simplifies deploying and managing applications in the cloud without the need for managing infrastructure.

## Prerequisites
- Docker Desktop (Docker Desktop or native CLI tools)
- An active **AWS account** with permissions for Elastic Beanstalk.
- Basic knowledge of Docker and AWS Elastic Beanstalk.

## Steps to Recreate the Project

### Creating a Dockerfile
-The `Dockerfile` serves as the instruction set to build a container image. It:
1. Pulls the base **Nginx** image.
2. Replaces the default `index.html` file with a custom one.
3. Exposes the web server to receive HTTP traffic.

```dockerfile
# Dockerfile
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

### Building a Docker Image
-Use the following command to build your custom image:
-sudo docker build -t my-web-app .
-The specifies the current directory containing the `Dockerfile`.

### Running the Docker Container Locally
-Run the container to verify functionality:
-sudo docker run -d -p 8080:80 my-web-app

-Access the application locally by navigating to `http://localhost:8080`.

### Deploying on AWS Elastic Beanstalk
1. **Package the application**: Create a `.zip` file containing the `Dockerfile` and `index.html`.
2. **Deploy on EBS**:
   - Create a new Elastic Beanstalk application in the AWS Management Console.
   - Upload the `.zip` file.
   - Deploy the application.

## Project Insights
- **Key Learning**: Deploying containers on AWS EBS is straightforward and efficient for web applications.

# Node.js App Deployment using Docker, AWS ECR & ECS

## Project Overview

In this project, I deployed a Node.js application on AWS using Docker containers. The main idea was to containerize the app, push the image to AWS ECR, and then run it using ECS.

---

## Tools & Technologies

* Linux (Ubuntu)
* Docker
* AWS EC2
* AWS ECR
* AWS ECS
* AWS CLI
* CloudWatch

---

## What I Did (Workflow)

1. Launched an EC2 instance and installed Docker
2. Cloned my Node.js project from GitHub
3. Built a Docker image of the application
4. Created an ECR repository and pushed the image
5. Created an ECS cluster and task definition
6. Ran the container using ECS
7. Accessed the application using public IP

---

## Steps I Followed

### 1. EC2 Setup

* Created an Ubuntu EC2 instance
* Connected using SSH

### 2. Docker Setup

* Installed Docker
* Added user to docker group

### 3. Build Docker Image

```bash
docker build -t node-todo-app .
```

### 4. Push Image to ECR

* Created repository in ECR
* Logged in using AWS CLI
* Tagged and pushed the image

### 5. ECS Deployment

* Created ECS cluster
* Created task definition with ECR image
* Ran task to deploy container

---

## Issue I Faced

I was not able to access the application using the public IP.

### Solution

The issue was with the security group. I added an inbound rule:

* Port: 8000
* Source: 0.0.0.0/0

After that, the application worked fine.

---

## Output

The application was successfully deployed and accessible via the public IP of the ECS task.

---

## What I Learned

* How Docker works in real projects
* How to use AWS ECR to store images
* How ECS runs containers
* Basic troubleshooting in AWS networking
* Importance of IAM roles and permissions

---

## Final Thoughts

This project helped me understand the complete flow of deploying a containerized application on AWS. It also gave me hands-on experience with real DevOps tools.

---

## Author

Vanshit

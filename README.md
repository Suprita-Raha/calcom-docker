# Calcom Docker
This project demonstrates deploying and running the open-source scheduling platform, Cal.com, using Docker Compose in [Ubuntu](https://ubuntu.com/).

---
# Table of Contents
1. [Introduction](#introduction)
2. [Clone calcom/docker](#clone-calcomdocker)
3. [Change into the directory](change-into-the-directory)
4. [Prepare your configuration](prepare-your-configuration)
5. [Pre-Pull the images](pre-pull-the-images)
6. [Start Cal.com via Docker Compose](start-calcom-via-docker-compose)
7. [Access Cal.com](#access-calcom)
8. [Video](#video)

---

## Introduction
 
[Cal.com](https://cal.com/) is an open-source scheduling platform designed to simplify meeting and appointment management for individuals and teams. It provides seamless integration with popular calendar systems, customizable booking pages, and a user-friendly interface, making scheduling effortless and efficient.  

### Key features of Cal.com

- **Customizable Scheduling**: Create personalized booking links with advanced options tailored to your needs.  
- **Team Management**: Coordinate availability across teams and simplify group scheduling.  
- **Integration-Ready**: Works with popular tools like Google Calendar, Microsoft Outlook, and Zoom.  
- **Scalable**: Whether you're an individual or a large organization, Cal.com adapts to your requirements.  
- **Privacy First**: Open-source and self-hostable, giving you complete control over your data.  
![image](https://github.com/user-attachments/assets/e3f8002a-5e93-41d9-a6c0-e0339649882b)

### Why use Calcom Docker?
Using Cal.com Docker simplifies the deployment and management of the Cal.com scheduling platform. Here are the key reasons for choosing the Docker approach:  
1. **Easy Setup**: Docker Compose automates the process of setting up the application along with its dependencies, like the database and Prisma Studio.  
2. **Portability**: Docker ensures the application runs consistently across various environments, eliminating compatibility issues.  
3. **Scalability**: Dockerized services can easily scale to meet the needs of small teams or large enterprises.  
4. **Customization**: You can tailor configurations like database URLs, environment variables, and more to match specific requirements.  
5. **Isolation**: Running Cal.com in Docker containers ensures the app and its dependencies don’t interfere with other services on the host machine.  
6. **Community Support**: The [Cal.com Docker repository](https://github.com/calcom/docker) is maintained by the community, providing pre-built images and configurations for a smoother experience.  

Docker Compose makes Cal.com deployment faster, easier, and more reliable, especially for users evaluating the platform or running it with minimal modifications.

---
## Clone calcom/docker
Clone the Docker repository for Cal.com using the following command:
```bash
git clone https://github.com/calcom/docker.git
```
---
## Change into the directory
Navigate to the cloned `docker` directory:
```bash
cd docker
```
---
## Prepare your configuration
Rename `.env.example` to `.env` and then update `.env`:
```bash
cp .env.example .env
```
---
## Pre-Pull the images
Run the following command to pre-pull the images:
```bash
docker compose pull
```
This will use the default image locations as specified by `image:` in the `docker-compose.yaml` file.

---
## Start Cal.com via Docker Compose
Ensure that `DATABASE_URL` is configured for an available database, then run:
```bash
docker compose up -d calcom
```
---
## Access Cal.com
Open a browser to `http://localhost:3000`, or your defined `NEXT_PUBLIC_WEBAPP_URL`.  
The first time you run Cal.com, a setup wizard will initialize. Setup credentials defined in `docker-compose.yml` and login.

---
## Video
[Calcom Docker.webm](https://github.com/user-attachments/assets/5107614a-f8c0-4914-b1f2-67c396fac2b5)

---

*Special thanks to Ashok Harnal Sir for his guidance and the Calcom/docker community for sharing the repository.*

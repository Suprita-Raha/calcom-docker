# calcom-docker

# Table of Contents
1. [Introduction](#introduction)
2. [Step 1: Clone calcom/docker](#step-1-clone-calcomdocker)
3. [Step 2: Change into the directory](#step-2-change-into-the-directory)
4. [Step 3: Prepare your configuration](#step-3-prepare-your-configuration)
5. [Step 4: Pre-Pull the images](#step-4-pre-pull-the-images)
6. [Step 5: Start Cal.com via Docker Compose](#step-5-start-calcom-via-docker-compose)  
   - [5.1: Run the Complete Stack](#51-run-the-complete-stack)  
   - [5.2: Run Cal.com Web App and Prisma Studio with a Remote Database](#52-run-calcom-web-app-and-prisma-studio-with-a-remote-database)  
   - [5.3: Run Only the Cal.com Web App](#53-run-only-the-calcom-web-app)
7. [Access Cal.com](#access-calcom)
8. [Video](#video)

---

## Introduction
 
[Cal.com](https://cal.com/) is an open-source scheduling platform designed to simplify meeting and appointment management for individuals and teams. It provides seamless integration with popular calendar systems, customizable booking pages, and a user-friendly interface, making scheduling effortless and efficient.  

Key features of Cal.com include:  
- **Customizable Scheduling**: Create personalized booking links with advanced options tailored to your needs.  
- **Team Management**: Coordinate availability across teams and simplify group scheduling.  
- **Integration-Ready**: Works with popular tools like Google Calendar, Microsoft Outlook, and Zoom.  
- **Scalable**: Whether you're an individual or a large organization, Cal.com adapts to your requirements.  
- **Privacy First**: Open-source and self-hostable, giving you complete control over your data.  
![image](https://github.com/user-attachments/assets/e3f8002a-5e93-41d9-a6c0-e0339649882b)

This guide explains how to set up and run Cal.com using Docker Compose for a streamlined and efficient deployment process.  

---

## Step 1: Clone calcom/docker
Clone the Docker repository for Cal.com using the following command:
```bash
git clone https://github.com/calcom/docker.git
```

## Step 2: Change into the directory
Navigate to the cloned `docker` directory:
```bash
cd docker
```

## Step 3: Prepare your configuration
Rename `.env.example` to `.env` and then update `.env`:
```bash
cp .env.example .env
```

## Step 4: Pre-Pull the images
Run the following command to pre-pull the images:
```bash
docker compose pull
```
This will use the default image locations as specified by `image:` in the `docker-compose.yaml` file.

**Note:** To aid with support, by default, Scarf.sh is used as a registry proxy for download metrics.

## Step 5: Start Cal.com via Docker Compose
### 5.1: Run the Complete Stack
To run the complete stack, which includes:
- A local Postgres database
- Cal.com web app
- Prisma Studio

Use the following command:
```bash
docker compose up -d
```

### 5.2: Run Cal.com Web App and Prisma Studio with a Remote Database
Ensure that `DATABASE_URL` is configured for an available database, then run:
```bash
docker compose up -d calcom studio
```

### 5.3: Run Only the Cal.com Web App
Ensure that `DATABASE_URL` is configured for an available database, then run:
```bash
docker compose up -d calcom
```

## Access Cal.com
Open a browser to `http://localhost:3000`, or your defined `NEXT_PUBLIC_WEBAPP_URL`.  
The first time you run Cal.com, a setup wizard will initialize. Setup credentials defined in `docker-compose.yml` and login.

## Video


---

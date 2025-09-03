# Project Setup Guide
## Folder Structure
/PVM_Project
│
├── /front-end-01
│   ├── Dockerfile
│   ├── src/
│   └── dist/
│
├── /Backend
│   ├── Dockerfile
│   ├── src/
│   └── dist/
│
├── docker-compose.yml
├── docker-compose.prod.yml
└── .dockerignore
________________________________________
# Explanation: -
There are two Docker files, one for the front end and the other for the backend. The services can be activated using the docker-compose.yml and docker-compose.prod.yml files. All the files are present in the repository 
# 1. Building Docker Images
## Frontend
## 1.	Navigate to the frontend directory:
`cd frontend`
## 2.	Build the Docker image:
`docker build -t muhammadsharjeel403/frontendimage .`
## Backend
## 1.	Navigate to the backend directory:
`cd ../backend`
## 2.	Build the Docker image:
`docker build -t muhammadsharjeel403/backendimage .`

#  2. Running with Docker Compose
## Development Environment
## 1.	Start services:
`docker-compose up -d`
## 2.	Stop services:
`docker-compose down`
## Production Environment
## 1.	Start services with production configuration:
`docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d`
## 2.	Stop services:
`docker-compose -f docker-compose.yml -f docker-compose.prod.yml down`

# 3. Testing Connectivity Between Services
## 1.	Access the frontend:
Open your browser and go to `http://localhost:5000`
## 2.	Access the backend:
Open your browser and go to `http://localhost:49428`
## 3.	Verify inter-service communication:
o	Ensure both services are on the same network (app-network).
o	Use service names (frontend, backend) instead of localhost for internal communication.

# 4. Pushing Images to Docker Hub
## 1.	Log in to Docker Hub:
`docker login
## 2.	Tag the frontend image:
`docker tag muhammadsharjeel403/frontendimage muhammadsharjeel403/frontendimage:latest`
## 3.	Push the frontend image:
`docker push muhammadsharjeel403/frontendimage:latest`
## 4.	Tag the backend image:
`docker tag muhammadsharjeel403/backendimage muhammadsharjeel403/backendimage:latest`
## 5.	Push the backend image:
`docker push muhammadsharjeel403/backendimage:latest`



# Outfit AI Docker Compose Setup

This project consists of two services: a backend API and a frontend application. Both services are containerized using Docker, and this docker-compose.yml file orchestrates their deployment.
Overview

    Backend: A Flask-based API for the Outfit AI service running on port 8000.
    Frontend: A React-based frontend application running on port 3000 and connected to the backend API.

Prerequisites

Before running the Docker Compose setup, ensure you have the following installed:

    Docker
    Docker Compose

Running the Application

    Clone this repository (or navigate to your project directory).

    Build and start the containers with the following command:

    docker-compose up --build

    This will pull the necessary images (if not already available), build the containers, and start the services.

Services
Backend

    Image: brandonrafaellovelyno/outfit-ai-be:1.1
    Port: 8000
    Environment Variables:
        FLASK_ENV=production: Specifies that the Flask app should run in production mode.

The backend service will expose a Flask API on port 8000 of your local machine.
Frontend

    Image: brandonrafaellovelyno/outfit-ai-fe:1.0
    Port: 3000
    Environment Variables:
        NEXT_PUBLIC_BACKEND_URL=http://localhost:8000: The frontend will communicate with the backend API at this URL.

The frontend service will run a React application on port 3000 of your local machine. It is set to make API requests to the backend on http://localhost:8000.
Accessing the Application

    Frontend: Open your browser and navigate to http://localhost:3000 to access the frontend.
    Backend: The API will be available at http://localhost:8000, but typically you will interact with it via the frontend.

Stopping the Application

To stop the running containers, use the following command:

docker-compose down

This will stop and remove the containers.
Additional Configuration
Customizing Environment Variables

You can customize the environment variables for both the frontend and backend services by modifying the docker-compose.yml file. For example, you can change the backend URL or modify the Flask environment mode.

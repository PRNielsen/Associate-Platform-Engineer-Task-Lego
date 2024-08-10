# Associate Platform Engineer Task - Lego Group
## Project Overview
This project is a Python/Flask based API that interacts with a Redis database to manage Homer Simpson quotes. It includes Docker configurations for easy setup and a CI/CD pipeline using GitHub Actions. The project demonstrates the following key components:

 - Dockerization: Dockerfiles for the Python/Flask based API application and Redis.
 - Deployment: Deployment definitions via Docker Compose.
 - CI/CD Pipeline: A GitHub Actions workflow for building, testing, and potentially deploying the application.

## Prerequisites
Before setting up the project, ensure you have the following installed:
 - Docker Desktop
 - Git
 - Make (optional, for using the provided Makefile)

## Setup
### Clone the Repository
Clone the repository to your local machine:

git clone https://github.com/PRNielsen/Associate-Platform-Engineer-Task-Lego.git
cd Associate-Platform-Engineer-Task-Lego

### Environment
#### Choose Your Environment
This project supports both development and production environments. Select the environment that suits your needs:
##### Development Setup

For development, a docker-compose.override.yml file is included, which maps the local project directory to the Docker container. This allows for live updates without needing to rebuild the image each time.

To start the development environment with live updates:

`make up`

Key Features:
 - Real-time code updates.
 - Easy debugging and testing.

##### Production Setup
For production, use the standard docker-compose.yml file without the volume mapping provided in the override file. This ensures a consistent and isolated environment, which is critical for production stability.

To start the production environment:

`docker-compose -f docker-compose.yml up -d`

Key Features:
 - Consistent, isolated environment.
 - Ideal for deploying to production servers.

#### Environemnt Variables
The project uses environment variables to configure the Redis connection. By default, these are set in the docker-compose.yml file:

```
environment:
  - REDIS_ENDPOINT=redis
  - REDIS_PORT=6379
```

If needed, you can override these by creating a .env file in the root directory.

## Usage
### Build and Run the Application
You can build and run the application using Docker Compose. This will start both the Flask app and the Redis database:

`make up`

This command will:
 - Build the Docker images for the application.
 - Start the application and Redis containers.

Once the containers are running, you can access the application at http://localhost:5000.

### Running Tests
To run the test suite, use the following command:

`make test`

This command will:
 - Spin up the necessary containers.
 - Execute the tests defined in app_test.py.

### Stopping the Application
To stop the running containers:

`make down`

### Cleaning Up
If you need to remove all containers, volumes, and clean up the environment:

`make clean`

## CI/CD Pipeline
The project includes a GitHub Actions workflow defined in .github/workflows/ci.yml. This workflow automatically builds, tests, and can potentially deploy the application when changes are pushed to the main branch or a pull request is created.
Key Pipeline Steps:
 - Build: Builds the Docker images.
 - Test: Runs the test suite inside a Docker container.
 - (Optional) Deploy: The pipeline can be extended to deploy the Docker images to Docker Hub or another registry.
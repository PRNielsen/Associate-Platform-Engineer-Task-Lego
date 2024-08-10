Development Setup:
For ease of development, a docker-compose.override.yml file is included to map the local project directory to the Docker container. This allows for live updates without rebuilding the image.

Production Setup:
For production, the standard docker-compose.yml file should be used, which does not include volume mapping, ensuring consistency and isolation of the environment.
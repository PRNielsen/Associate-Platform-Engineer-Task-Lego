# Makefile

# Variables
DOCKER_COMPOSE = docker-compose

# Default target (executed if no specific target is provided)
.PHONY: all
all: build

# Build the Docker containers
.PHONY: build
build:
	$(DOCKER_COMPOSE) build

# Run the application
.PHONY: up
up:
	$(DOCKER_COMPOSE) up

# Run the tests
.PHONY: test
test:
	$(DOCKER_COMPOSE) run test

# Stop the containers
.PHONY: down
down:
	$(DOCKER_COMPOSE) down

# Clean up the Docker environment
.PHONY: clean
clean: down
	$(DOCKER_COMPOSE) rm -f
	$(DOCKER_COMPOSE) down --volumes --remove-orphans
# Makefile

DOCKER_COMPOSE = docker-compose

.PHONY: all
all: build

.PHONY: build
build:
	$(DOCKER_COMPOSE) build

.PHONY: up
up:
	$(DOCKER_COMPOSE) up

.PHONY: test
test:
	$(DOCKER_COMPOSE) run test

.PHONY: down
down:
	$(DOCKER_COMPOSE) down

.PHONY: clean
clean: down
	$(DOCKER_COMPOSE) rm -f
	$(DOCKER_COMPOSE) down --volumes --remove-orphans
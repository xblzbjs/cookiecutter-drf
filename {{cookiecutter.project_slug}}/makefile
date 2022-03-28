SHELL := /bin/bash

.PHONY: help
help: ## Show this help
	@egrep -h '\s##\s' $(MAKEFILE_LIST) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-20s\033[0m %s\n", $$1, $$2}'

.PHONY: install
install: ## Poetry install
	poetry install

.PHONY: test
test: ## Run tests
	pytest tests/

.PHONY: run ## Run the Django server
	./manage.py runserver_plus

migration: ## Make and run migrations
	./manage.py makemigrations

migrate: ## Make and run migrate
	./manage.py migrate


start: install migration migrate run ## Install requirements, apply migrations, then start development server

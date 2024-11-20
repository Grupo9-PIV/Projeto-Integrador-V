# Path do ambiente virtual do Poetry
VENV := $(shell poetry env info --path)

# Alvos
.PHONY: setup install dev run lint format test coverage clean

setup:
	@echo "Instalando pipx..."
	python3 -m pip install --user pipx
	python3 -m pipx ensurepath
	@echo "Instalando Poetry com pipx..."
	pipx install poetry
	@echo "Poetry instalado com sucesso!"

install:
	poetry install --without dev

dev:
	poetry install --with dev

run:
	poetry run task run

lint:
	poetry run task lint

format:
	poetry run task format

test:
	poetry run task test

coverage:
	poetry run task post_test

clean:
	rm -rf $(VENV)
	rm -rf .pytest_cache .ruff_cache coverage .coverage coverage.xml htmlcov

PROJECT = piikkibot
VENV = venv
PYTHON = $(VENV)/bin/python3
PIP = $(VENV)/bin/pip

run:
	$(PYTHON) -m $(PROJECT).main

install: requirements.txt requirements-dev.txt
	python3 -m venv $(VENV)
	$(PIP) install --upgrade pip
	$(PIP) install -r requirements.txt 
	$(PIP) install -r requirements-dev.txt
	$(shell ln -sf ../../hooks/pre-commit .git/hooks/pre-commit)
	$(shell chmod +x hooks/pre-commit)


lint:
	$(PYTHON) -m black .
	$(PYTHON) -m isort .
	$(PYTHON) -m mypy .

test:
	$(PYTHON) -m pytest

clean:
	rm -rf **/__pycache__
	rm -rf **/.pytest_cache
	rm -rf **/.mypy_cache
	rm -rf $(VENV)
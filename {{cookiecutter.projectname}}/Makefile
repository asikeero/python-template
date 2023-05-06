PROJECT = {{ cookiecutter.projectname }}
RUFFFLAGS = ""
PYTESTFLAGS = ""


all: .built

.built: pyproject.toml
	poetry install
	$(shell ln -sf ../../hooks/pre-commit .git/hooks/pre-commit)
	$(shell chmod +x hooks/pre-commit)
	touch .built

lint: .built
	@echo "**** black ****"
	poetry run black --check $(PROJECT) tests
	@echo "**** vulture ****"
	poetry run vulture $(PROJECT)
	@echo "**** mypy ****"
	poetry run mypy -p $(PROJECT)
	@echo "**** ruff ****"
	poetry run ruff check $(RUFFFLAGS) $(PACKAGE) tests

format: .built
	@echo "**** black ****"
	poetry run black $(PROJECT) tests
	@echo "**** ruff ****"
	poetry run ruff check --fix $(PACKAGE) tests

test: .built
	poetry run pytest $(PYTESTFLAGS)



clean:
	poetry env remove --all
	git clean -Xdf
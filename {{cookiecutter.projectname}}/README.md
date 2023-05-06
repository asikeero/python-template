# {{ cookiecutter.projectname }}

## Installation

This project uses **python {{ cookiecutter.pyversion }}** so make sure you have that installed. You also need [poetry](https://python-poetry.org/) as a meta-dependency. Recommended way is to install poetry with [pipx](https://pypa.github.io/pipx/) to run it isolated.

After cloning the repo, you can use commands in the `Makefile` to do common tasks. Start by running 
```
make all
```
to let poetry initiate a virtual environment and install dependencies. This will also install a pre-commit hook into your `.git` folder, that runs the `make lint` command before committing. It will abort the commit if errors are found. You can fix them with running `make format`
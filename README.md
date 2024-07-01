# python-boilerplate

This template servces as a standard DS template for production level repos. This project is a somewhat opinionated scaffolding & configuration for a Python application managed with poetry.

It has example ways of using github actions for commits/pushes, pre-commit flags used in a standard for the DS department and shows briefly how to create pytest unit tests.

Additionally, you should be following the standard python style guide located here: https://github.com/kengz/python

## Installation

This project requires python>=3.11, though it can be modified to use previous versions.

This project additionally requires that `poetry` is installed.

**Install project & dependencies**

```bash
poetry install
```

**Activate Virtual Environment**

```bash
source .venv/bin/activate # MacOS/Linux

.venv/Scripts/activate.bat # Windows
```

*Note: Poetry allows you to activate the virtual environment via `poetry shell`, but you can only enter the venv like this in one console at a time. Activating via virtual environment bypasses this restriction.*

**Install Pre-Commit Hook**

```bash
pip install pre-commit
pre-commit install
```

## Dependencies

Dev/Test dependencies are discussed in the appropriate sections.
The only hard dependencies for this project is `poetry`.

## Files

- pyproject.toml
    - Contains package information including dependencies & some configuration.
    Dependencies are specified using less precise version restrictions.
- poetry.lock
    - Not included in the template repo. This is because you will have to put your own dependencies and then once you update the `pyproject/toml` file you can run `poetry lock` in terminal.
    - Auto generated file specifying exact dependencies (like a pip freeze). Best practice is to keep this in source control so that deploying the app deploys the exact dependencies used during testing. This file should *not* be edited manually. It will automatically update when changing dependencies or when running `poetry lock`.
- .pre-commit-config.yaml
    - Configuration for pre-commit hooks

## Updates

You will want to update the `package_name` directory with your custom name. There will be down-hill changes in that directories `__init__.py` file as well as the pytests in the `./tests/` directory. However it should be clear using this template how youneed to change them.

No changes are needed to the `./.github/` directory. All the testing is currently done through poetry and has pytest and mypy checkes to pass Github Actions.

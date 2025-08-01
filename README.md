# backstage-trial

[![Build Status](https://github.com/ONS-Innovation/backstage-trial/actions/workflows/ci.yml/badge.svg)](https://github.com/ONS-Innovation/backstage-trial/actions/workflows/ci.yml) <!-- Uncomment after enabling MegaLinter by renaming [mega-linter.yml.example](.github/mega-linter.yml.example) to mega-linter.yml and moving it to the [.github/workflow](.github/workflow) folder
[![Build Status](https://github.com/ONS-Innovation/backstage-trial/actions/workflows/mega-linter.yml/badge.svg)](https://github.com/ONS-Innovation/backstage-trial/actions/workflows/mega-linter.yml)
-->
[![Build Status](https://github.com/ONS-Innovation/backstage-trial/actions/workflows/codeql.yml/badge.svg)](https://github.com/ONS-Innovation/backstage-trial/actions/workflows/codeql.yml)

[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Linting: Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/charliermarsh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)
[![Checked with mypy](https://www.mypy-lang.org/static/mypy_badge.svg)](https://mypy-lang.org/)
[![poetry-managed](https://img.shields.io/badge/poetry-managed-blue)](https://python-poetry.org/)
[![License - MIT](https://img.shields.io/badge/licence%20-MIT-1ac403.svg)](https://github.com/ONS-Innovation/backstage-trial/blob/main/LICENSE)

---

## Quick Setup: Enable MegaLinter CI

This repository includes a pre-configured MegaLinter workflow for automated code quality checks, but it needs to be manually enabled:

**To activate MegaLinter:**
1. Rename [.github/mega-linter.yml.example](.github/mega-linter.yml.example) to `.github/mega-linter.yml`
2. Move the file from [.github](.github) to the [.github/workflows](.github/workflows) folder
3. Commit and push the change

**Why this step is needed:**
GitHub Actions security restrictions prevent automatic creation of workflow files during template initialisation. Learn more about [GitHub Token permissions and workflow limitations](https://docs.github.com/en/actions/security-guides/automatic-token-authentication#permissions-for-the-github_token).

Once enabled, MegaLinter will automatically run on all Pull Requests and commits to `main`, checking:
- Python code quality (Ruff, Black, Pylint, MyPy)
- GitHub Actions workflows
- Documentation formatting
- Shell scripts, Dockerfiles, and more

---

First Repository to for the Backstage_Trial

> **IMPORTANT**: This README was generated from a template. Please update it with specific information about your project, including:
> - Detailed project description and purpose
> - Specific installation requirements
> - Usage examples and API documentation
> - Contributing guidelines specific to your project
> - Any project-specific compliance requirements

---

## Compliance Checklist

Before you start developing, please ensure you've completed the following compliance requirements:

- [ ] **CODEOWNERS**: Update `.github/CODEOWNERS` with the appropriate team/individuals responsible for this repository.
- [ ] **README**: Update this README with project-specific information (remove this notice when done)
- [ ] **Repository Settings**: Ensure branch protection rules are enabled (should be automatic if using template setup)
- [ ] **Security**: Review and configure security settings appropriate for your project
- [ ] **License**: Verify the LICENSE file is appropriate for your project
- [ ] **Dependencies**: Review and update dependencies as needed for your project

---

## Table of Contents

[//]: # (:TODO: Enable link checking once https://github.com/tcort/markdown-link-check/issues/250 is resolved.)
<!-- markdown-link-check-disable -->
- [Getting Started](#getting-started)
    - [Pre-requisites](#pre-requisites)
    - [Installation](#installation)
- [Development](#development)
    - [Run Tests with Coverage](#run-tests-with-coverage)
    - [Linting and Formatting](#linting-and-formatting)
- [Contributing](#contributing)
- [License](#license)
<!-- markdown-link-check-enable -->

## Getting Started

To get a local copy up and running, follow these simple steps.

### Pre-requisites

Ensure you have the following installed:

1. **Python**: Version specified in `.python-version`. We recommend using [pyenv](https://github.com/pyenv/pyenv) for
   managing Python versions.
2. **[Poetry](https://python-poetry.org/)**: This is used to manage package dependencies and virtual
   environments.
3. **[Docker](https://docs.docker.com/engine/install/)**
4. **Operation System**: Ubuntu/MacOS

### Installation

1. Clone the repository and install the required dependencies.

   ```bash
   git clone https://github.com/ONS-Innovation/backstage-trial.git
   ```

2. Install dependencies

   [Poetry](https://python-poetry.org/) is used to manage dependencies in this project. For more information, read
   the [Poetry documentation](https://python-poetry.org/).

   To install all dependencies, including development dependencies, run:

   ```bash
   make install-dev
   ```

   To install only production dependencies, run:

   ```bash
   make install
   ```

3. Run the application

   ```bash
   make run
   ```

## Development

Get started with development by running the following commands.
Before proceeding, make sure you have the development dependencies installed using the `make install-dev` command.

A Makefile is provided to simplify common development tasks. To view all available commands, run:

```bash
make
```

### Run Tests with Coverage

The unit tests are written using the [pytest](https://docs.pytest.org/en/stable/) framework. To run the tests and check
coverage, run:

```bash
make test
```

### Linting and Formatting

Various tools are used to lint and format the code in this project.

#### Python

The project uses [Ruff](https://github.com/astral-sh/ruff), [pylint](https://pylint.pycqa.org/en/latest/index.html)
and [black](https://black.readthedocs.io/en/stable/) for linting and formatting of the Python code.

The tools are configured using the `pyproject.toml` file.

To lint the Python code, run:

```bash
make lint
```

To auto-format the Python code, and correct fixable linting issues, run:

```bash
make format
```

#### MegaLinter (Lint/Format non-python files)

[MegaLinter](https://github.com/oxsecurity/megalinter) is utilised to lint the non-python files in the project.
It offers a single interface to execute a suite of linters for multiple languages and formats, ensuring adherence to
best practices and maintaining consistency across the repository without the need to install each linter individually.

MegaLinter examines various file types and tools, including GitHub Actions, Shell scripts, Dockerfile, etc. It is
configured using the `.mega-linter.yml` file.

To run MegaLinter, ensure you have **Docker** installed on your system.

> Note: The initial run may take some time to download the Docker image. However, subsequent executions will be
> considerably faster due to Docker caching. :rocket:

To start the linter and automatically rectify fixable issues, run:

```bash
make megalint
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License

See [LICENSE](LICENSE) for details.

# CI/CD Tools and Practices Final Project Template

## Project Name
ci-cd-final-project

## Project Details

- **Project name:** IMB-exercise - CI/CD Tools and Practices Final Project
- **Application:** Hit Counter Service, a Python Flask REST API for creating,
  reading, updating, deleting, and listing named counters.
- **Course:** IBM / Coursera CI/CD Tools and Practices.
- **Template:** [IBM Skills Network final project template](https://github.com/ibm-developer-skills-network/vselh-ci-cd-final-project-template).
- **Template revision:** b9d5eaf742a801e50ff6db025c867c8795f8ea51.

## Repository Structure

- `service/`: Flask application and HTTP utilities.
- `tests/`: Counter API unit tests.
- `requirements.txt`: Runtime, lint, and test dependencies.
- `setup.cfg`: nose, coverage, and flake8 configuration.
- `Dockerfile` and `Procfile`: Application runtime definitions.
- `bin/setup.sh`: Setup script for the course's Linux lab environment.
- `.github/workflows/workflow.yml`: Empty template file for the CI exercise.
- `.tekton/tasks.yml`: Empty template file for the Tekton task exercise.

## Setup

The upstream template targets Python 3.9 and nose 1.3.7. Its legacy test stack
does not run unchanged on Python 3.12. Use an isolated compatible environment
for the course exercise; Python 3.9 is end-of-life.

In the course-provided Linux lab environment, the template's setup command is:

```bash
bash bin/setup.sh
```

That script installs system packages, changes the default Python, and modifies
the shell profile. It is not a Windows PowerShell setup script and should not
be run on a general-purpose machine without reviewing it first. After running
it in the intended lab environment, close the shell and open a new one to
activate the configured virtual environment.

In an existing compatible virtual environment, install dependencies and check
the application from the repository root:

```bash
python -m pip install -r requirements.txt
flake8 service tests --count --max-complexity=10 --max-line-length=127 --statistics
nosetests -v --with-spec --spec-color
```

## Tasks

This repository currently contains the upstream starter application. The GitHub
Actions workflow and Tekton tasks are intentionally empty, matching the template,
and must be implemented as part of the final project. Successful CI runs,
OpenShift deployment, screenshots, and application logs are still to be collected.

## License And Attribution

Starter code by Skills Network, imported from the IBM template linked above.
Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE).

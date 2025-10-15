---
layout: default
title: Programming Standard
permalink: /iMarina/Developer-Guide/Programming-standard/
parent: Developer Guide
grand_parent: iMarina
nav_order: 1
---



# 🧭 Programming Standards for developers

This document defines the main tools and practices used in the iMarina-load project to ensure consistent development, testing, and deployment workflows.


## 🐳 Docker 

Docker is used to containerize the application and provide a consistent environment across development, testing, and production.
All builds and executions should be done through the provided `Dockerfile` and `docker-compose.yml`. 

Developers can use this command in bash to access the container shell for debugging.
```shell
  docker-compose run --rm app sh
```


Use the provided `Dockerfile` and `docker-compose.yml` to build and run the iMarina-load service in a containerized environment.  
Build image  `docker compose up --build` to start the application with mounted input/output directories and configured secrets.

### A Dockerfile contain this:

Dockerfile: Builds a lightweight Python 3.12 Alpine image that installs dependencies and 
runs the main script with predefined input file paths.

**File content:**
```dockerfile

# image python
FROM python:3.12-alpine3.20

LABEL authors="yourname"

RUN mkdir -p /input

# work directory in the container
WORKDIR /app

# copy at the app
COPY ./src /app/src
COPY ./requirements.txt /app

# install requirements
RUN pip install --no-cache-dir -r requirements.txt

# script python for main
CMD ["python", "/app/src/main.py", "--imarina-input", "/input/iMarina.xlsx", "--a3-input", "/input/A3.xlsx", "--countries-dict", "/input/countries.xlsx", "--jobs-dict", "/input/Job_Descriptions.xlsx"]

```

### A docker-compose contain this:

Defines a service that builds and runs the iMarina-load container, mounts input/output folders, 
and securely injects FTP credentials as secrets for automated data processing.

**File content:**
```yaml

services:
  app:
    image: yourname/imarina-load:latest
    build: .
    container_name: iMarina_docker
    volumes:
    - ./input:/app/input
    - ./output:/app/output
    - ./uploads:/app/uploads

    secrets:
      - FTP_HOST
      - FTP_PASSWORD
      - FTP_PORT
      - FTP_USER
    stdin_open: true
    tty: true
    command: >
      sh -c "python /app/src/main.py --imarina-input /app/input/iMarina.xlsx --a3-input /app/input/A3.xlsx --countries-dict /app/input/countries.xlsx --jobs-dict /app/input/Job_Descriptions.xlsx --step build"

secrets:
  FTP_HOST:
    file: ./secrets/FTP_HOST
  FTP_PASSWORD:
    file: ./secrets/FTP_PASSWORD
  FTP_PORT:
    file: ./secrets/FTP_PORT
  FTP_USER:
    file: ./secrets/FTP_USER

```


### Useful Docker Commands

- **Build the Docker image manually**  
```shell
   docker build -t yourtagname/imarina-load --progress=plain .
```


 
                   
## 🧪 Testing

Automated testing is handled with **pytest** to ensure code reliability and prevent regressions.
Pytest is the standard testing framework for Python and used for both unit and integration testing.
Before building or deploying the application, all tests must pass successfully.  


### Unit Testing
Developers are expected to write **unit tests** for all new features and bug fixes.  
Each module or function should have corresponding tests located under the `tests/` directory.  
Tests can be executed locally with:
```shell
 pytest -v
```


Install the pytest library we will use to create and run the tests.
```shell

pip install pytest
```

### Test creation:   
Test functions beginning with `test_` are written in files with the same name. 
All test files are located in the `tests/` directory at the root of the project `Desktop/iMarina-load/tests`.

Exemple name test:
`test_main.py`

At the top of this file, you must import the necessary classes and, most importantly, `src.main`.
Our main is in the `src` folder.


This is an example of test of function name **is_visitor**
```python

from datetime import date, datetime

from src.main import Researcher, is_visitor


def test_is_visitor():
    researcher = Researcher(
        ini_date=date(2025, 9, 30),
        end_date=date(2025, 10, 5),
        code_center=4)
    assert is_visitor(researcher) == True

```

#### Pytest Usage and Configuration
A `pytest.ini` file must be created in the project root directory  
(e.g., `Desktop/iMarina-load/`) to ensure pytest correctly resolves imports and test paths.

**File content:**
```ini
[pytest]
pythonpath = .
```


Pytest uses the `pytest.ini` file to define global configuration settings.  
The option `pythonpath = .` adds the project root directory (`.`) to the `PYTHONPATH`, allowing Python to correctly locate modules inside the `src/` folder.

All test files should be placed in the `tests/` directory, located at the same level as the `src/` folder.  

Once the configuration is complete, save the file and run the tests to verify that everything works as expected.


### Executing pytest

Developers must execute all test commands from the project root directory to avoid import errors:

```shell
   cd ~/Desktop/iMarina-load
```

If necessary, the project root can be added to the PYTHONPATH manually:

```shell

export PYTHONPATH=$PYTHONPATH:/home/<your_username>/Desktop/iMarina-load


```


### 🧪 Automation Testing (pytest)

Developers can run tests using the following commands:

- **Run all tests**
```shell
  pytest -v
```
Runs all unit and integration tests in the project.  


- **Display print statements or logs during tests**

```shell
  pytest -s -v
```
Useful for debugging and observing intermediate outputs.


- **Stop on the first failure**

```shell
  pytest -x
```
Stops test execution as soon as a test fails.

- **Run specific tests by name**
```shell
   pytest -k "test_name"
``` 
Executes only tests matching the given name or keyword.







    





















<!-- TODO Git branching model / * GitHub Actions (test stage)  / * IDE (PyCharm) -->
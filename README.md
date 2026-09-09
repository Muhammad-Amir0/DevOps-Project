# DevOps Project
![CI Pipeline](https://github.com/Muhammad-Amir0/DevOps-Project/actions/workflows/ci.yml/badge.svg)

A Dockerized Flask web application with automated testing, code quality checks, and a CI pipeline using GitHub Actions.

## Project Overview

This project demonstrates a basic DevOps workflow by combining:

- Python Flask web application
- Automated testing with Pytest
- Code quality checks with Ruff
- Docker containerization
- Git and GitHub version control
- GitHub Actions CI pipeline

## Application Endpoints

### Home

```text
GET /



## Step 1 — Add the Home response

### Home

```text
GET /
```

Returns:

```text
Hello from DevOps CI/CD Pipeline - Version2!
```

### Home

```text
GET /
```

Returns:

```text
Hello from DevOps CI/CD Pipeline - Version2!
```

### Health Check

```text
GET /health
```

Returns:

```json
{
  "status": "healthy"
}
```


## Technologies Used

- Python 3.12
- Flask
- Pytest
- Ruff
- Docker
- Git
- GitHub
- GitHub Actions


## Run the Application Locally

Create and activate the virtual environment:

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

Run the application:

```powershell
python app.py
```

Open in your browser:

```text
http://127.0.0.1:5000/
```



## Run Tests

Run the automated tests with:

```powershell
pytest

2 passed



## Run Ruff

Run the code quality check with:

```powershell
ruff check .

All checks passed!


## Run with Docker

Build the Docker image:

```powershell
docker build -t devops-project .


## CI Pipeline

GitHub Actions automatically runs the following whenever changes are pushed to the `main` branch:

1. Checkout the source code
2. Set up Python 3.12
3. Install project dependencies
4. Run Pytest
5. Run Ruff
6. Build the Docker image

The workflow is defined in:

```text
.github/workflows/ci.yml



## Project Structure

```text
DevOps-Project/
├── .github/
│   └── workflows/
│       └── ci.yml
├── .dockerignore
├── .gitignore
├── Dockerfile
├── README.md
├── app.py
├── requirements.txt
└── test_app.py




## Learning Objectives

This project was created to practice practical DevOps concepts including:

- Version control
- Continuous Integration
- Automated testing
- Code quality automation
- Docker containerization
- GitHub Actions
- Basic CI/CD workflow design


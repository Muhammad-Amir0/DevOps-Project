# DevOps Project

![CI Pipeline](https://github.com/Muhammad-Amir0/DevOps-Project/actions/workflows/ci.yml/badge.svg)

A Dockerized Flask web application with automated testing, code quality checks, Docker Hub image publishing, and a CI/CD pipeline using GitHub Actions.

## Project Overview

This project demonstrates a practical DevOps workflow by combining:

* Python Flask web application
* Automated testing with Pytest
* Code quality checks with Ruff
* Docker containerization
* Git and GitHub version control
* GitHub Actions CI/CD
* Docker Hub image publishing
* SHA-based Docker image versioning
* Manual Docker image rollback

## Application Endpoints

### Home

```text
GET /
```

Returns:

```text
Hello from DevOps CI/CD Pipeline - Version3!
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

* Python 3.12
* Flask
* Pytest
* Ruff
* Docker
* Docker Hub
* Git
* GitHub
* GitHub Actions

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

Health check:

```text
http://127.0.0.1:5000/health
```

## Run Tests

Run the automated test suite:

```powershell
pytest
```

The project currently includes tests for both application endpoints.

## Run Ruff

Run the code quality check:

```powershell
ruff check .
```

## Run with Docker

Build the Docker image:

```powershell
docker build -t devops-project .
```

Run the container:

```powershell
docker run -d -p 5000:5000 --name devops-app devops-project
```

Open the application:

```text
http://localhost:5000/
```

Stop the container:

```powershell
docker stop devops-app
```

Remove the container:

```powershell
docker rm devops-app
```

## CI/CD Pipeline

GitHub Actions automatically runs the CI/CD workflow whenever changes are pushed to the `main` branch.

The pipeline performs the following steps:

1. Checkout the source code
2. Set up Python 3.12
3. Install dependencies
4. Run Pytest
5. Run Ruff
6. Build the Docker image
7. Log in to Docker Hub
8. Tag the image with the Git commit SHA
9. Tag the image as `latest`
10. Push the SHA-tagged image to Docker Hub
11. Push the `latest` image to Docker Hub

The workflow is defined in:

```text
.github/workflows/ci.yml
```

## Docker Image Versioning

Each successful build receives a unique Docker image tag based on the Git commit SHA.

Example:

```text
muhammadamir0/devops-project:<commit-sha>
```

The same image is also tagged as:

```text
muhammadamir0/devops-project:latest
```

This allows previous versions to remain available for rollback.

## Manual Rollback

The project includes a manual rollback workflow using GitHub Actions.

To perform a rollback:

1. Open the GitHub repository.
2. Go to the **Actions** tab.
3. Select the **CI Pipeline** workflow.
4. Select **Run workflow**.
5. Enter the Docker image SHA tag to restore.
6. Run the workflow.

The rollback process:

```text
Previous SHA Image
       ↓
Pull Image
       ↓
Tag as latest
       ↓
Push latest to Docker Hub
```

The rollback functionality was tested successfully by restoring the previous image version and verifying that the `latest` tag had the same Docker digest as the selected previous version.

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
```

## Learning Objectives

This project was created to practice practical DevOps concepts including:

* Git and GitHub
* Continuous Integration
* Continuous Deployment concepts
* Automated testing
* Code quality automation
* Docker containerization
* Docker Hub
* GitHub Actions
* Docker image versioning
* CI/CD workflow design
* Manual rollback strategies

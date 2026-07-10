# Module 9

This module builds on the FastAPI Calculator by adding a PostgreSQL database and pgAdmin for data persistence and management, alongside continued use of FastAPI, Docker, and automated testing.

## Key Components

1. **Dockerfile** — Sets up a Docker container for a FastAPI Calculator Application by using the `mcr.microsoft.com/playwright/python:v1.47.0-noble` image as the base, installing necessary system packages and Python dependencies, creating a non-root user with sudo access, and configuring the environment to run the application.
2. **docker-compose.yml** — Defines a multi-service application, including a FastAPI web service, a PostgreSQL database, and pgAdmin for database management, specifying their configurations, health checks, dependencies, and networking to facilitate seamless integration and deployment.
3. **main.py** — Defines the FastAPI application, including API endpoints for basic arithmetic operations (add, subtract, multiply, divide) and serving the HTML page, utilizing Pydantic models for input validation and Jinja2 templates for rendering responses.
4. **app/operations.py** — Contains arithmetic functions (`add`, `subtract`, `multiply`, `divide`).
5. **templates/index.html** — The HTML frontend that interacts with the API.

## Database

This project uses **PostgreSQL** to persist calculation history, with **pgAdmin** as a web-based interface for managing the database directly.

- **Database:** `fastapi_db`
- **Tables:** `users`, `calculations` (linked by a foreign key on `user_id`)
- **pgAdmin access:** `http://localhost:5050`
  - Email: `admin@example.com`
  - Password: `admin`
  - Server host: `db` (Docker service name), Port: `5432`

## Setting Up the Development Environment

1. **Clone the repository:**
git clone https://github.com/enp23/assignment9.git

2. **Navigate to the project directory:**
cd assignment9

3. **Create a virtual environment:**
python -m venv venv
source venv/bin/activate  # On Windows use venv\Scripts\activate

4. **Install dependencies:**
pip install -r requirements.txt

5. **Run the application:**
uvicorn main:app --reload

7. **Access the application:**
   Open a web browser and navigate to `http://localhost:8000`.

8. **Stop the application:**
   Press `CTRL + C`.

### Running with Docker

9. **Build and start the application, database, and pgAdmin in Docker:**
docker compose up --build

## Docker Hub

[https://hub.docker.com/repository/docker/en23/assignment9/](https://hub.docker.com/repository/docker/en23/assignment9/)
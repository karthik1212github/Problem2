# Problem2
TALENTRAX TECHNOLOGIES-Backend Developer Screening Assignment

Q2. Imagine you are tasked with building a backend infrastructure for a new project.
Your goal is to design a scalable REST API structure using the specified
technologies and requirements. Below are the tasks you need to complete:
1. Create a system that returns test data on the `/v1/hello` and `/v2/hello` endpoints.
Design this system in a way that allows for easy scaling. You should also provide a
template for this sample project, which can be used as a starting point for future
development.
2. Expand the API by adding the following endpoints:
- /login: This endpoint should perform authentication using PostgreSQL (PSQL),
generate a unique UUID, save it as a cache in Redis, and return it to the user as a new
authorization header.
- /setName: Implement the ability to update a user's name. An authorization header
should be required for this endpoint.
- /getName: Create an endpoint to retrieve a user's name.
3. Develop an `init.sql` file that includes the database schema with proper indexing
and search optimization for PostgreSQL.
4. Prepare Docker and Docker Compose files for both production and development
environments. The APIs should utilize Nginx as an API proxy manager.
5. Demonstrate a basic understanding of microservices architecture and explain how
you would integrate this backend system with existing projects.

Project Stack:
- Framework: FastAPI
- Database: Asyncpg for PostgreSQL, Redis for caching
- ASGI Server: Uvicorn
- Production Server: Gunicorn
- Containerization: Docker, Docker Compose
- API Proxy Manager: Nginx
- Additional Technologies as Required


Basic Project Structure (for reference)

└── API/
├── static/
│ └── assets/
│ └── img/
│ └── happy.png
├── utils/
│ ├── helper/
│ │ └── helpme.py
│ ├── database/
│ │ └── psql.py
│ └── redis/
│ └── redis.py
├── web/
│ ├── __init__.py
│ ├── v1/
│ │ ├── __init__.py
│ │ └── somefile.py
│ └── v2/
│ ├── __init__.py
│ └── somefile.py
├── constants.py
├── init.sql
├── version.py
├── main.py
├── runserver.py
├── Dockerfile
├── gunicorn.py.ini
├── compose.yaml
├── Makefile
├── nginx.conf
├── readme.md
├── .env
├── .env.local
└── .env.prod



Solution:

Project Structure:

└── API/
│   ├── app/
│   │   ├── v1/
│   │   │   ├── __init__.py
│   │   │   └── hello.py
│   │   ├── v2/
│   │   │   ├── __init__.py
│   │   │   └── hello.py
│   │   ├── auth/
│   │   │   ├── __init__.py
│   │   │   └── login.py
│   │   ├── user/
│   │   │   ├── __init__.py
│   │   │   ├── set_name.py
│   │   │   └── get_name.py
│   │   └── __init__.py
│   ├── static/
│   │   └── assets/
│   │       └── img/
│   │           └── happy.png
│   ├── utils/
│   │   ├── helper/
│   │   │   └── helpme.py
│   │   ├── database/
│   │   │   └── psql.py
│   │   └── redis/
│   │       └── redis.py
│   ├── constants.py
│   ├── init.sql
│   ├── version.py
│   ├── main.py
│   ├── runserver.py
│   ├── Dockerfile
│   ├── gunicorn.py.ini
│   ├── compose.yaml
│   ├── Makefile
│   ├── nginx.conf
│   ├── readme.md
│   ├── .env
│   ├── .env.local
│   └── .env.prod

Components:
Endpoints:

- '/v1/hello' and '/v2/hello': Return test data.
- '/login' : Authenticate using PostgreSQL, generate a unique UUID, save it in Redis, and return as a new authorization header.
- '/setName' : Update a user's name (requires authorization header).
- '/getName' : Retrieve a user's name (requires authorization header).

Database Schema:
- 'init.sql': Define the schema with proper indexing and search optimization for PostgreSQL.

Docker Setup:
- 'Dockerfile': Build a FastAPI app image using Uvicorn and Gunicorn.
- 'docker-compose.yaml': Define services for FastAPI, PostgreSQL, Redis, and Nginx.


Configuration Files:
- 'gunicorn.py.ini': Gunicorn configuration.
- 'nginx.conf': Nginx configuration for API proxy.


Environment Configuration:
- '.env': Environment variables for development.
- '.env.local' : Environment variables for local development.
- '.env.prod': Environment variables for production.


Documentation:
- 'readme.md': Project documentation with setup instructions.


Microservices Architecture Integration:
-For seamless integration with existing projects using a microservices architecture:
-Expose necessary APIs as microservices.
-Employ message queues (e.g., RabbitMQ or Kafka) for asynchronous communication between microservices.
-Implement consistent authentication and authorization mechanisms across microservices.
-Ensure each microservice is independently deployable and scalable.

Technologies:

Framework: FastAPI
Database: Asyncpg for PostgreSQL, Redis for caching
ASGI Server: Uvicorn
Production Server: Gunicorn
Containerization: Docker, Docker Compose
API Proxy Manager: Nginx

This structure provides a scalable foundation for a FastAPI-based REST API project. 
It is designed for modularity, allowing for easy expansion and modification as additional 
features and endpoints are added in the future.





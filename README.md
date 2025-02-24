# FastAPI Trading Orders API

## Features
- Accepts trade orders via `POST /orders`
- Fetches orders via `GET /orders`
- Stores orders in PostgreSQL (via Docker)
- Supports WebSockets for real-time order updates
- Deployed on AWS EC2 with Docker

## Setup & Run
```sh
git clone <repo-url>
cd <project-folder>
docker-compose up --build

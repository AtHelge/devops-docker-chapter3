
# 2.11 – My dev environment

Project: https://github.com/AtHelge/password-generator-web.git

A Flask password generator, deployed on Render via Dockerfile and yaml file.


## What I did
Added a `docker-compose.yaml` for local development with two services:

- **web** – built from the Dockerfile. The code is bind-mounted into the container and Flask runs in debug mode, so changes are live without rebuilding.

- **redis** – counts how many passwords have been generated. The app connects via the service name `redis` (`REDIS_HOST=redis`).

The Dockerfile is unchanged and still used for production on Render, where the app runs without Redis and hides the counter.

Start app with : `docker compose up` → http://localhost:5000
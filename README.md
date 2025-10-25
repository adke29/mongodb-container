# [DEPRECATED] mongodb-container

A lightweight Docker Compose project to spin up a standalone MongoDB container using environment variables for easy configuration.

## Features

- Simple setup with a single `docker-compose.yml`
- Configurable via `.env` file
- Uses the official MongoDB Docker image
- Suitable for local development and testing

## Prerequisites

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- `.env` file in the root directory (see below)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/mongodb-container.git
cd mongodb-container
```

### 2. Create a .env file

Create a .env file in the root directory with the following contents:

```env
MONGODB_INITDB_ROOT_USERNAME=mongoadmin
MONGODB_INITDB_ROOT_PASSWORD=securepassword
```

### 3. Start the MongoDB container

```bash
docker compose up -d
```

MongoDB will be available at mongodb://{{MONGODB_INITDB_ROOT_USERNAME}}:{{MONGODB_INITDB_ROOT_PASSWORD}}@localhost:27017/{{DATABASE}}?authSource=admin

### 4. Stopping the Container

```bash
docker compose down
```

## Directory Structure

```bash
mongodb-container/
├── .env
├── docker-compose.yml
└── README.md
```

## Common Issues

### Permission Denied

If you got error `Permission denied [system:13]: "/data/db/journal"`, run this command:

```bash
chmod 777 ./data
```

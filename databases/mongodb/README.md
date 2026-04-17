# MongoDB

This directory contains the configuration for a shared MongoDB database instance.

## Tools Configured

*   **MongoDB**: A document-oriented NoSQL database program.

## Goal

To provide a centralized and shared NoSQL database backend that can be consumed by multiple services within the homelab environment.

## Usage in this Project

MongoDB is configured to store data and configuration on the host under `/mnt/docker-data/databases/mongodb/`. It reads its root credentials securely via Docker secrets and exposes port `27017` on the shared `dockernet` network, allowing other containerized services (such as Komodo) to connect to it.

## Installation Steps

1.  Navigate to this directory:
    ```bash
    cd mongodb
    ```
2.  Create a `secrets` directory and the required secret files for the root credentials:
    ```bash
    mkdir -p secrets
    echo "your_secure_db_password" > secrets/db_password.txt
    echo "root_user" > secrets/db_user.txt
    ```
3.  Start the database:
    ```bash
    docker compose up -d
    ```

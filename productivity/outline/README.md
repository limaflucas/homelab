# Productivity: Outline Wiki

This directory contains the configuration for the Outline knowledge base.

## Tools Configured

*   **Outline**: A fast, collaborative, modern knowledge base for teams.
*   **PostgreSQL**: Database for Outline.
*   **Redis**: In-memory data structure store used as a cache by Outline.
*   **MinIO**: S3-compatible object storage used by Outline to store attachments and images.
*   **Authelia**: Open-source authentication and authorization server (OIDC provider) used to log in to Outline.

## Goal

To provide a robust, self-hosted Wiki and knowledge management system with rich features, secure authentication, and scalable storage.

## Usage in this Project

Outline is configured as a comprehensive stack. It relies on Postgres for relational data, Redis for caching, MinIO for S3-compatible file storage, and Authelia for Single Sign-On (SSO) via OIDC. The Outline application itself is exposed on port `3001`.

## Installation Steps

1.  Navigate to this directory:
    ```bash
    cd productivity/outline
    ```
2.  Create the `secrets` directory and populate the required files:
    ```bash
    mkdir -p secrets
    echo "your_db_password" > secrets/db_password.txt
    echo "outline_user" > secrets/db_user.txt
    echo "your_minio_admin" > secrets/minio_root_user.txt
    echo "your_minio_password" > secrets/minio_root_password.txt
    ```
3.  Ensure you have a `.env` file configured for Outline (refer to Outline documentation).
4.  Generate or place the required SSL certificates in a `certs/` directory, specifically creating the combined CA file as noted in the docker-compose (`cat ./certs/outline-pgsql.crt ./certs/outline-authelia.crt > ./certs/combined-ca.crt`).
5.  Configure Authelia by providing `configuration.yml` and `users_database.yml` in the expected Authelia volume.
6.  Start the stack:
    ```bash
    docker compose up -d
    ```
7.  Access Outline at `http://<your-server-ip>:3001` (or via your configured proxy).

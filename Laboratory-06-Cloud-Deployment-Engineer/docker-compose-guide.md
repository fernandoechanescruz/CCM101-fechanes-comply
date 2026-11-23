# Docker Compose Guide — Nextcloud + MariaDB

## What does the `services:` block do?
It lists every container that belongs to the application stack. Each entry under `services:` (here, `database` and `app`) turns into its own container with its own image, environment variables, and settings. Docker Compose reads the block and builds and starts all of them together.

## How did the Nextcloud app container find the database container?
It used the `MYSQL_HOST=database` environment variable. Docker Compose automatically sets up a private network for all the services in the file and registers each service name (such as `database`) as a DNS hostname that other containers on that network can resolve. The `app` container can therefore reach the database just by connecting to the hostname `database`, with no IP address required.

## Difference between `docker run` and `docker-compose up -d`
`docker run` launches a single container, and every configuration option has to be typed out as a command-line flag each time. `docker-compose up -d` reads one YAML file and starts every service defined in it, including networking and environment variables, using a single command. This makes it much less error-prone for applications made up of multiple containers.

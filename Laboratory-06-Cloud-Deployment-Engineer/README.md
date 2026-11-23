# Laboratory Activity 6: Mission 6 – The Cloud Deployment Engineer

## Mission Overview
This lab introduces Infrastructure as Code (IaC) through Docker Compose. Instead of starting containers manually one at a time, I used a single YAML configuration file to deploy a two-tier private cloud storage application made of Nextcloud and MariaDB.

## Objectives
- Describe what a multi-tier application architecture is
- Understand the purpose and structure of a docker-compose.yml file
- Create configuration files on the command line using nano
- Deploy a multi-container application with Docker Compose
- Write up deployment procedures and IaC principles in Markdown

## Commands Executed
- `mkdir nextcloud-deployment`, `cd nextcloud-deployment`
- `nano docker-compose.yml`
- `docker-compose up -d`
- `docker-compose ps`
- `docker-compose down`

## Skills Learned
- Writing a valid, correctly indented YAML configuration file
- Launching several linked containers with one command
- Understanding how Docker Compose's internal networking and DNS let containers locate each other by service name
- Documenting Infrastructure as Code for other engineers

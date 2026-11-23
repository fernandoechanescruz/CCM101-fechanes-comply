# Laboratory Activity 7: Mission 7 – The Cloud Operations Engineer

## Mission Overview
This lab is about observability. I established the baseline health of a host server, deployed a containerized Nginx web server, and generated both normal and error traffic against it. I then used Docker's logging and metrics tools to show that the infrastructure is healthy and ready for a surge in traffic.

## Objectives
- Use built-in Linux CLI tools to keep track of host CPU, memory, and disk capacity
- Deploy a web container and follow its performance in real time
- Produce web traffic and pull out the application access logs for analysis
- Turn raw performance data into a readable technical report

## Monitoring Commands Executed
- `free -h` — check memory usage
- `df -h` — check disk storage
- `top` — view live CPU load and running processes
- `docker run -d --name client-website -p 8080:80 nginx` — deploy the container
- `curl http://localhost:8080` — simulate normal traffic
- `curl http://localhost:8080/hidden-admin-page` — simulate a broken request
- `docker logs client-website` — retrieve application logs
- `docker stats` — view real-time container resource usage

## Skills Learned
- Setting a host-level performance baseline before deployment
- Producing and interpreting HTTP access logs, including error codes
- Reading live container resource metrics such as CPU, memory, and network I/O
- Telling monitoring (metrics) apart from logging (events)

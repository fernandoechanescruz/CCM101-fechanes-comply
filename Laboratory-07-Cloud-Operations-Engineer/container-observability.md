# Container Observability

## 404 Error Log Entry
```
172.17.0.1 - - [23/Nov/2026:12:05:37 +0000] "GET /hidden-admin-page HTTP/1.1" 404 153 "-" "curl/8.5.0" "-"
```

Application logs are essential for troubleshooting because they capture the exact request, timestamp, and response code of each event. This allows an engineer to identify what a user did and where it went wrong instead of guessing. Without logs, a vague complaint such as "the site is broken" would be almost impossible to trace back to a specific cause.

## Real-Time Resource Usage (docker stats)
At the time of the screenshot, the `client-website` container was using:
- **Memory Usage:** 2.723MiB / 1.859GiB
- **CPU %:** 0.00%

These numbers confirm the container is running efficiently and is nowhere
near exhausting the host's available CPU or memory.

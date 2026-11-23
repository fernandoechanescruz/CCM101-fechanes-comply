# Backup Script Guide

## The Script (backup.sh)
```bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

# Create the backup directory if it does not exist
mkdir -p $BACKUP_DIR

# Compress the source directory into a tarball (.tar.gz)
tar -czf $BACKUP_DIR/backup_$TIMESTAMP.tar.gz $SOURCE_DIR

echo "Backup completed successfully at $TIMESTAMP!"
```

## What `chmod +x backup.sh` Did
By default, Linux treats a newly created text file as plain data and not as a program, even when it contains valid shell commands. This stops the system from accidentally running random text files. `chmod +x backup.sh` gives the file **execute permission**, which tells Linux that it is allowed to run as a program. Without this step, running `./backup.sh` fails with a "Permission denied" error.

## Cron Expression Breakdown: `0 2 * * * /root/backup.sh`
| Field | Value | Meaning |
|---|---|---|
| Minute | `0` | At minute 0 |
| Hour | `2` | At 2 AM (02:00, 24-hour time) |
| Day of Month | `*` | Every day of the month |
| Month | `*` | Every month |
| Day of Week | `*` | Every day of the week |

Taken together, this schedules `/root/backup.sh` to run automatically every night at exactly **2:00 AM**, with no human involvement.

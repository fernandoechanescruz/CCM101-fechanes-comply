# Laboratory Activity 9: Mission 9 – The Cloud Automation Engineer

## Mission Overview
This lab removes human error from a recurring operational task. I wrote a Bash script that automatically compresses and backs up a client's application data, then scheduled it with the Linux cron scheduler to run every night at 2:00 AM, so nobody has to press a button.

## Objectives
- Understand the basic syntax of a Bash shell script, including variables and simple commands
- Write and save an executable script using the nano text editor
- Change Linux file permissions with chmod
- Understand task scheduling and the syntax of a Linux crontab
- Document automation code and cron job configuration in Markdown

## Commands Executed
- `mkdir app-data` / `echo "..." > app-data/data.txt` — created dummy client data
- `nano backup.sh` — wrote the automated backup script
- `chmod +x backup.sh` — granted execute permission to the script
- `./backup.sh` — ran the script, producing a compressed `.tar.gz` backup
- `crontab -e` — added a cron entry: `0 2 * * * /root/backup.sh`
- `crontab -l` — verified the installed schedule

## Skills Learned
- Writing and running a Bash shell script from the terminal
- Controlling Linux file permissions with chmod
- Scheduling repeating automated tasks with cron
- Writing clear documentation of automation code and scheduling syntax for other engineers

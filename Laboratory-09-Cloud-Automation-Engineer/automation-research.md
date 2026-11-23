# Automation Research

## Bash Script
A Bash script is a plain text file that holds a series of Linux commands, which the shell runs in order from top to bottom, just as if a person had typed them in one at a time. The `#!/bin/bash` line at the very top is known as a "shebang." It tells the operating system which interpreter, in this case Bash, should be used to read and run the rest of the file.

## Variables
Programmers use variables such as `$BACKUP_DIR` rather than retyping the full folder path each time, because it makes scripts easier to maintain and much less prone to mistakes. If the backup location ever changes, only the single variable assignment at the top of the script has to be edited, instead of searching through the file and changing every command that uses that path.

## Cron Job
A cron job is a task scheduled with Linux's built-in `cron` daemon, which automatically runs a given script or command at a chosen time, date, or interval without any human involvement. It is vital for cloud operations because routine tasks such as backups cannot rely on someone remembering to run them by hand every day. Cron takes the human factor out of the process entirely.

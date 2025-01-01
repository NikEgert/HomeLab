# Backup Script with Cron Integration

During my Homelab journey, I faced the challenge of automating data backups to preserve snapshots effectively. To address this, I developed a Python script that seamlessly archives files and integrates with Cron for task scheduling. This setup ensures backups are executed periodically without requiring manual intervention.

## Overview of the Backup Script

The Python backup script performs the following tasks:

1. **Directory or File Backup**: It compresses a specified file or directory into a `.tar` archive and stores it in a specified destination directory.
2. **Automated Cleanup**: It checks the age of existing backups in the destination directory and deletes backups older than a specified number of days.
3. **Error Handling**: It handles cases where the source directory, file, or destination directory is missing or invalid.

### Script Workflow

1. **Input Parameters**:

- `source_directory`: The directory containing the file or directory to be backed up.
- `destination_directory`: The directory where backups will be stored.
- `saved_item`: The specific file or directory to be backed up.
- `days_before_deletion`: The number of days after which backups will be considered old and deleted.

2. **Backup Process**:

- Ensures the source directory exists.
- Ensures the destination directory exists, creating it if necessary.
- Compresses the specified file or directory into a .tar archive named with the current date.

3. **Cleanup Process**:

- Iterates over existing .tar files in the destination directory.
- Parses dates from file names to determine their age.
- Deletes backups older than the specified threshold.

The script can be found [here](https://github.com/NikEgert/Item_Backup)

### Example Command

In my case, I use this script to backup the minecraft server hosted in a docker container.

```bash
python3 /path/to/script.py /var/lib/docker/volumes /home/Minecraft/backup minecraftdata 4
```

## Cron Job

### What is Cron?

Cron is a time based job scheduler in Linux. It allows users to schedule tasks (cron jobs) to run automatically at specified times or intervals.

### Writing the Cron Job

open the crontab editor:

```bash
crontab -e
```

append the line:

```bash
0 0 * * 0 python3 /home/Backup/script.py /var/lib/docker/volumes /home/Minecraft/backup minecraftdata 4
```

This cron job runs the backup script every day at 3:00 AM.

Save and Exit the file.

### TroubleShooting

Cron Job logs can be checked using:

```bash
grep CRON /var/log/syslog
```

### General guide to Cron

```conf

# ┌───────────── minute (0 - 59)
# │ ┌───────────── hour (0 - 23)
# │ │ ┌───────────── day of the month (1 - 31)
# │ │ │ ┌───────────── month (1 - 12)
# │ │ │ │ ┌───────────── day of the week (0 - 6) (Sunday to Saturday)
# │ │ │ │ │
# │ │ │ │ │
# │ │ │ │ │
# * * * * * <command to execute>

```

(source [wikipedia](https://en.wikipedia.org/wiki/Cron))

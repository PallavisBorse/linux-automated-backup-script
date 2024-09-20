#!/bin/bash

# Configuration
SOURCE_DIR="/path/to/source"  # Directory to back up
BACKUP_DIR="/path/to/backup"  # Backup destination
LOG_FILE="/path/to/backup/backup.log"  # Log file
EMAIL="your-email@example.com"  # Email address for notifications

# Create backup directory if it doesn't exist
mkdir -p "$BACKUP_DIR"

# Perform backup
timestamp=$(date +"%Y%m%d%H%M%S")
backup_file="$BACKUP_DIR/backup_$timestamp.tar.gz"

echo "Starting backup: $timestamp" >> "$LOG_FILE"
tar -czf "$backup_file" "$SOURCE_DIR" >> "$LOG_FILE" 2>&1

if [ $? -eq 0 ]; then
    echo "Backup completed successfully: $backup_file" >> "$LOG_FILE"
    echo "Backup completed successfully" | mail -s "Backup Success" "$EMAIL"
else
    echo "Backup failed" >> "$LOG_FILE"
    echo "Backup failed" | mail -s "Backup Failure" "$EMAIL"
fi

-Make the Script Executable:
  You can do this by running:
    chmod +x backup_script.sh
-Commit the Script to Your Repository:
  Add the script file to your Git repository:
    git add backup_script.sh
    git commit -m "Add backup script"
    git push

-Set Up Cron Job for Automated Backups
Edit the Cron Job Configuration:
Open the crontab editor by running:
  crontab -e
Add the following line to schedule the script to run daily at midnight (for example):
  0 0 * * * /path/to/backup_script.sh
Save and exit the editor.
Document the Cron Job Setup in Your GitHub Repository:

Since you're not using the terminal, we’ll add the cron job configuration instructions to your repository.
Update Your README.md with Cron Job Setup Instructions:

Include a section in your README.md file detailing how to set up a cron job for users who clone your repository.
Here’s the content to add to the README.md:
## Automating Backups with Cron

To schedule automatic backups, you can set up a cron job to run the `backup_script.sh` at regular intervals.

### Steps:
1. Open the crontab editor:
   ```bash
   crontab -e
Add the following line to run the backup script daily at midnight:
  0 0 * * * /path/to/backup_script.sh
Save and exit the editor. This will automate the backup process, ensuring that your important files are backed up every day.

# Linux Project Overview

## Project Title: Automated Backup Script

**Description:**
This project involves creating an automated backup script for Linux systems. The script is designed to regularly back up important files and directories to a specified backup location, ensuring that critical data is safely stored and easily recoverable in case of system failures or data loss.

**Features:**
- **Automated Backups:** The script performs backups at scheduled intervals.
- **Customizable Backup Paths:** Users can specify which directories to back up and where to store the backups.
- **Logging:** The script maintains a log file to track backup activities and any errors encountered.
- **Email Notifications:** Sends email alerts upon successful backups or if any issues arise.

**Technologies Used:**
- Shell Scripting
- Cron Jobs (for scheduling backups)
- Email Configuration (for notifications)

**Setup Instructions:**
1. Clone the repository: `git clone <repo-url>`
2. Navigate to the project directory.
3. Configure the script by editing the `backup_config.sh` file to specify backup paths and email settings.
4. Set up a cron job to run the script at desired intervals.

**Usage:**
Run the script manually using `bash backup_script.sh` or let the cron job handle automatic backups.

**Troubleshooting:**
- Ensure the script has executable permissions: `chmod +x backup_script.sh`
- Check the log file for detailed error messages if the backup fails.

**Contact:**
For any questions or issues, please reach out to [borsepallavi630@gmail.com].


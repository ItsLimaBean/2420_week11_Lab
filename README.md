# 2420 Week 11 Lab

## Backup Script

### Setting up ssh keys
1. Generate key-pair using `ssh-keygen`
2. Copy the contents of `<keygen>.pub` to ~/.ssh/authorized_keys in your backup sever

### Installing the script
1. Navigate to `/opt/`
2. Create a folder called `backup-script`
3. Place the `backup-script` file and `config` in that folder
4. Add execution permissions using `chmod +x backup-script config`

### Configuring the script

The scripts backup script is located in the config besides the script.

* BACKUP_DIRS
    * Specify the directories you wish to back up.
    * Example: `("/home/user/stuff" "/home/user/work")`
* BACKUP_LOCATION
    * Specify the location on the backup server you wish to use for storing you backups
    * Example: `"/home/user/backup"`
* BACKUP_IP
    * User and ip address of your backup server
    * Example: `"user@127.0.0.1"`

### Installing the service/timer
1. Navigate to `/etc/systemd/system/`
2. Place `backup.service` and `backup.timer` in this directory
3. Run `sudo systemctl daemon-reload`
4. Enable the service with `sudo systemctl enable backup.service`
5. Enable the timer with `sudo systemctl enable backup.timer`
6. Check the status using `sudo systemctl status backup.service` and `sudo systemctl status backup.timer`
7. If there are no errors, you've successfully installed the service and timer needed.
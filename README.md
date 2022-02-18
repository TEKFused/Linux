# Linux
Helpful Linux commands and scripts.

## Cron jobs

#### Edit Cron jobs using nano.
```bash
# Path to root and cPanel user cron files: /var/spool/cron/
sudo env EDITOR=nano crontab -e
```
### List ALL cron jobs for ALL users.

```bash
for user in $(cut -f1 -d: /etc/passwd); do crontab -u $user -l; done
```

## File System Permissions

### View ownership.
```bash
ls -l /path/to/file
```
### View permissions.
```bash
stat -c "%a %n" 
```

### View all groups and group members.
```bash
getent group
```

### Add a user to a group.
```bash
gpasswd -a user group
```
### Remove a user from a group.
```bash
gpasswd -d user group
```

## Commands

#### Number of users logged in today.
```bash
bc <<< "$(lastlog -b 0 -t 1 | wc -l)-1"
```

#### Get the last 25 failed logins.
```bash
lastb -an 25 | grep "$(date +%b)"
```

#### Get the last 25 succesful logins.
```bash
last -an 25 | grep "$(date +%b)"
```

#### Get the commands run today.
```bash
history | grep "$(date +%F)"
```

#### Get the number of commands run today.
```bash
history | grep "$(date +%F)" | wc -l
```

#### Get the 10 largest files in a user's home directory.
```bash
du -ahx ~/ | sort -rh | head -10
```

#### Search for text in files throughout the file system.
```bash
grep -rn '/home/mcog/public_html/wp-content/' -e 'portal/media'
```

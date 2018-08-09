# Linux
Helpful Linux commands and scripts.

## Commands

#### Edit Cron jobs using nano.
```bash
sudo env EDITOR=nano crontab -e
```

#### Number of users logged in today.
```bash
bc <<< "$(lastlog -b 0 -t 1 | wc -l)-1
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

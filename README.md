# Linux
Helpful Linux commands and scripts.

## Commands

#### Number of users logged in today.
bc <<< "$(lastlog -b 0 -t 1 | wc -l)-1

#### Get the last 25 failed logins.
lastb -an 25 | grep "$(date +%b)"

#### Get the last 25 succesful logins.
last -an 25 | grep "$(date +%b)"

#### Get the commands run today.
history | grep "$(date +%F)"

#### Get the number of commands run today.
history | grep "$(date +%F)" | wc -l

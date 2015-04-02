# dolibarr-backup
Backup my dolibarr instance

## Installation

make a copy of env.template as env

copy env and backup file to /usr/local/dolibarr

## Configuration

Edit env file and modify the following to match YOUR setup

```
MYSQLHOST=localhost
MYSQLUSER=dolibarr 
MYSQLPASSWORD=yourpassword
MYSQLDB=dolibarr
DOCUMENTS=/var/lib/dolibarr/documents
BACKUPPATH=/path/to/backups
MAXBACKUP=30
```

Note : MAXBACKUP is the number of backup to keep. Once you reach this number, the oldest backup is removed.

## Planification

Create a cron job to execute the script

```
crontab -e 

00 00 * * * /usr/local/dolibarr/backup 
06 00 * * * /usr/local/dolibarr/backup 
12 00 * * * /usr/local/dolibarr/backup 
18 00 * * * /usr/local/dolibarr/backup
```

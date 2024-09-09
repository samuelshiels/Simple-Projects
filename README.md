# Simple-Projects

## Backup

Backup files and directories for services and media

- Backup locally to /srv/backup/<service_name>
- Remote backup to network storage
- Cloud backup to a storage provider (B2) via rclone
- Backup a source directory via rsync
- Specify excludes
- From a directory also specify specific file patterns via include-from to only backup
- Record start and finish time
- Record total size of the backup
- Plot a graph of the relative backup size to itself to monitor growth
- Detect and log errors

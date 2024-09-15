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


## Local File Hosting

- Build a REST Server
- Specify a data standard for ingesting a `File Name` `File MIME Type` and `Data`
- Restrict file types to a small set of web browser compatible image formats
- Parse file data from base64 to the format needed to write to disk
- Generate a short, configurable, random ASCII string
- Store the value in a database with the non-`Data` values to ensure uniqueness
- Write the file to disk using the MIME Type to set extension with random string
- Ensure the file can be seen in the Web Server
- In the response to the inbound request return a URL the sender can use to view the file


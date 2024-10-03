# Simple-Projects

## Backup

Backup files and directories for services and media

Build a series of reusable and generic scripts to:

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

A locally accessible file upload and hosting service

- Build a REST Server
- Specify a data standard for ingesting a `File Name` `File MIME Type` and `Data`
- Restrict file types to a small set of web browser compatible image formats
- Parse file data from base64 to the format needed to write to disk
- Generate a short, configurable, random ASCII string
- Store the value in a database with the non-`Data` values to ensure uniqueness
- Write the file to disk using the MIME Type to set extension with random string
- Ensure the file can be seen in the Web Server
- In the response to the inbound request return a URL the sender can use to view the file

## Music Library

Scan your music files:

- Find all files in a root directory
  - Report on each file type (and size)
  - Allow multiple root directories
- Find all music files of a certain type (mp3/flac/ape/ogg)
  - Start with one format and add others afterwards
- Store their path and last modified times
- For each file extract a minimal set of tags to uniquely identify the track, artist and album
- Store this metadata somehow linked to the stored file data
- When rescanning the directory only rerun the tag retrieval on files whose modified time has updated
- Report files that are missing critical tag info
- Extract full size and thumbnail version of the front cover artwork
- Report if the front cover artwork is missing or low resolution (adjustable?)
- Record time taken for each step of file and tag retrieval and work out how to improve

### Music Player

From the previously built music library

- Retrieve your music catalogue and knowing that the minimum tags are present display the catalogue
  - Multiple views
    - By Artist
    - By Album
    - By Album Group
    - By Track
    - Multiple root directories
    - Display album artwork
      - Display other embedded images?
  - Play/Stop/Pause tracks/album/artists
  - Volume
  - Track scanning
  - Create playlist
    - Save in m3u format
  - Display reports for missing tags and artwork

 # Server - Client

 Dynamically create server processes with demand that allows clients to connect to them and run keep alive pings

 - Create a server application that has a socket running under a loop to process inbound messages. Print them to the console for now
 - Spawn this server into its own thread and store a reference to it.
   - The server should have some properties that can be retrieved such as total connected clients. Use a message channel.
 - Create multiple server processes using randomly chosen ports.
   - Handle ports being used already and retry
 - Create a client application that connects to the overall application
 - Have the client receive a port number of an existing server to then connect to.
   - Send a secret password for clients to present to a server to prevent clients from guessing.
 - Create new server processes if a server is full

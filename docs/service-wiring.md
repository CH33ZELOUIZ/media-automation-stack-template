# Service wiring

## Core app relationships

```text
Prowlarr -> Sonarr/Radarr/Lidarr indexers
Sonarr/Radarr/Lidarr -> qBittorrent download client
qBittorrent -> /data/downloads
Sonarr/Radarr/Lidarr -> /data/media
Jellyfin -> /data/media read-only
Jellyseerr -> Sonarr/Radarr requests
Unpackerr -> watches completed downloads and Servarr queues
```

## VPN network namespace

qBittorrent uses Gluetun's network namespace. Publish qBittorrent ports on Gluetun.

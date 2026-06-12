# App setup order

1. Start Gluetun and confirm VPN is healthy.
2. Start qBittorrent and set categories/download folders.
3. Start Prowlarr and configure indexers.
4. Add Sonarr/Radarr/Lidarr as apps in Prowlarr.
5. Configure qBittorrent as the download client in each Servarr app.
6. Set root folders under `/data/media`.
7. Start Jellyfin and add libraries from `/data/media`.
8. Start Jellyseerr and connect it to Jellyfin + Sonarr/Radarr.
9. Enable Unpackerr after API keys are generated.

# VPN + qBittorrent pattern

qBittorrent uses:

```yaml
network_mode: "service:gluetun"
```

That means qBittorrent has no independent network namespace. Its WebUI and torrent ports must be exposed on the Gluetun service, not on qBittorrent.

Operational notes:

- If Gluetun is down, qBittorrent network access is down too.
- Configure qBittorrent WebUI using the host port mapped on Gluetun.
- Keep the torrent port consistent between Gluetun and qBittorrent.
- Do not put app API keys or VPN credentials in the compose file; keep them in `.env`.

# Media Automation Stack Template

A public-safe Docker Compose template for a private homelab media automation stack.

It focuses on reusable structure rather than one person's live config:

- Gluetun VPN gateway
- qBittorrent routed through Gluetun
- Prowlarr
- Sonarr
- Radarr
- Lidarr
- Bazarr
- Jellyfin
- Jellyseerr
- Unpackerr
- Optional FlareSolverr

## What this template is for

Use this as a starting point for a private media server where download traffic should be isolated behind a VPN container and media managers share a consistent path contract.

## What is intentionally not included

- Real VPN credentials
- Indexer/tracker configuration
- API keys
- Private tracker names
- Media libraries
- Database/config backups
- Personal mount paths

## Quick start

```bash
git clone https://github.com/<your-user>/media-automation-stack-template.git
cd media-automation-stack-template
cp .env.example .env
# edit .env carefully
docker compose up -d
```

Then configure each app through its UI.

## Security and compliance notes

- Use only legal indexers/content for your jurisdiction and circumstances.
- Obey tracker/API/client rules.
- Do not publish passkeys, cookies, private tracker names, API keys, or screenshots that reveal them.
- Keep this stack private unless you understand the authentication surface of every app.
- qBittorrent is routed through Gluetun using `network_mode: service:gluetun`; expose only the ports you need on Gluetun.

## Docs

- [Path contract](docs/path-contract.md)
- [VPN/qBittorrent pattern](docs/vpn-qbittorrent.md)
- [Sanitization notes](docs/sanitization.md)

## License

MIT

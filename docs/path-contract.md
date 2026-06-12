# Path contract

This template uses one shared data mount inside every app:

```text
/data
├── downloads
│   ├── incomplete
│   └── complete
└── media
    ├── movies
    ├── tv
    └── music
```

Recommended download client paths:

- incomplete: `/data/downloads/incomplete`
- completed torrents: `/data/downloads/complete`

Recommended Servarr root folders:

- Sonarr: `/data/media/tv`
- Radarr: `/data/media/movies`
- Lidarr: `/data/media/music`

Why this matters:

- Hardlinks only work when downloader and media managers see the same filesystem.
- Remote path mappings become unnecessary when all apps agree on `/data`.
- Moving completed downloads instead of hardlinking wastes disk and breaks seeding expectations.

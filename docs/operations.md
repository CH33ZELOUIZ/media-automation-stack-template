# Operations

## What to monitor

- Gluetun health
- qBittorrent connectivity and free space
- Servarr import failures
- unpack/extraction errors
- Jellyfin playback/transcoding load
- disk usage on downloads and media paths

## Common path bug

If imports fail or hardlinks do not work, check that every app sees the same inside-container path. The template uses `/data` everywhere for this reason.

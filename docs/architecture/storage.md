# Storage

## Production Storage

`ust-axiom` provides the primary storage pool for production services.

| Pool | Layout | Drives | Purpose |
| --- | --- | --- | --- |
| nexus | RAIDZ2 | 8 × 512 GB SSD | Application data, AI models, media, general cloud storage |

## Dataset Layout

```text
/nexus/
├── immich/
│   ├── db/
│   └── uploads/
├── jellyfin/
└── media/
```


| Name | Mount Point | Used By |
| --- | --- | --- |
| `nexus/immich/db` | `/nexus/immich/db` | Immich (Database) |
| `nexus/immich/uploads` | `/nexus/immich/uploads` | Immich (Personal Photo Storage) |
| `nexus/jellyfin` | `/nexus/jellyfin` | Jellyfin (Metadata, Cache, Config)|
| `nexus/media` | `/nexus/media` | Jellyfin (Music & Video)|



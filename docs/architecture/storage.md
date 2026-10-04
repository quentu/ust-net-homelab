# Storage

## Production Storage

`ust-axiom` provides the primary storage pool for production services.

| Pool | Layout | Drives | Purpose |
| --- | --- | --- | --- |
| nexus | RAIDZ2 | 8 × 512 GB SSD | Application data, AI models, media, general cloud storage |

## Dataset Layout

```text
/nexus/
│
├── appdata/                 # Persistent service data
│   ├── immich/
│   ├── jellyfin/
│   └── ...
│
├── media/                   # Movies/music/books/etc.
│   ├── movies/
│   ├── tv/
│   ├── music/
│   └── books/
│
├── users/                   # Personal long-term files
│   └── quentu/
│       ├── documents/
│       ├── photos/
│       ├── school/
│       ├── career/
│       └── inbox/
│
├── software/                # software and installers archive for quick deployment
│   ├── appimages/
|   └── installers/
│
├── images/                  # System/virtualization images
│   ├── iso/
│   ├── vm/
│   ├── containers/
│   └── firmware/
│
├── archive/                 # Intentionally retained old data
│
├── backups/                 # Recoverable copies
│   ├── hosts/
│   ├── databases/
│   └── configs/
│
└── scratch/                 # Disposable
    ├── downloads/
    ├── staging/
    └── tmp/
```


| Name | Mount Point | Used By |
| --- | --- | --- |
| `nexus/appdata/immich/db` | `/nexus/appdata/immich/db` | Immich (Database) |
| `nexus/appdata/immich/uploads` | `/nexus/appdata/immich/uploads` | Immich (Personal Photo Storage) |
| `nexus/appdata/jellyfin` | `/nexus/appdata/jellyfin` | Jellyfin (Metadata, Cache, Config)|
| `nexus/media` | `/nexus/media` | (Music, Video, Books)|



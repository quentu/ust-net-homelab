# ust-net-homelab

---

## Infrastructure Overview

| Host | Role | VLAN | Primary Purpose |
|---|---|---:|---|
| `ust-overseer` | Management | VLAN 1 | Tailscale, management services, reverse proxy |
| `ust-axiom` | Production | VLAN 20 | NAS, Docker, media, AI workloads |
| `ust-vault` | Backup | TBD | Backup server |
| `ust-sentinel-01` | Lab / Compute | VLAN 30 | Proxmox node |
| `ust-sentinel-02` | Lab / Compute | VLAN 30 | Proxmox node |

See [`docs/architecture.md`](docs/architecture.md) for the full design.

---

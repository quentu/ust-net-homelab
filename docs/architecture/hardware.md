# Hardware

## Physical Systems

| Host | Platform | CPU | Memory | Primary Storage |
| --- | --- | --- | --- | --- |
| `ust-overseer` | NUC5i3MYBE | Intel Core i3-5010U  | 8GB DDR3 | 128GB M.2 SSD |
| `ust-axiom` | Custom built | Intel Core i5-9400F | 16 GB DDR4| 4TB ZFS pool |
| `ust-vault` | Mac mini 2012| Intel Core i5-3210M  | 4GB DDR3 | 1TB SATA SSD |
| `ust-sentinel-01` | HP Z210 | Intel Core i7-2600 | 16 GB DDR3 | 1TB SATA SSD |
| `ust-sentinel-02` | HP Z210 | Intel Core i7-2600 | 16 GB DDR3 | 1TB SATA SSD |
## Accelerators

`ust-axiom` uses an NVIDIA Tesla P40 (24GB VRAM) for local AI inference.

## Network Hardware

| Device | Model | Purpose |
| --- | --- | --- |
| Internet | Starlink | WAN connection |
| Router | TP-Link ER605 | Routing, DHCP, and VLAN gateways |
| Switch | Netgear GS608E | VLAN-aware switching |
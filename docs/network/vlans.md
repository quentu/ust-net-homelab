# VLANs

VLANs separate administrative access, production services, and experimental workloads.

| VLAN | Name | Subnet | Example Devices |
| --- | --- | --- | --- |
| 1 | Management | `192.168.10.0/24` | `ust-overseer`, router, switch, `archlinux` (personal workstation) |
| 20 | Production | `192.168.20.0/24` | `ust-axiom`, production services |
| 30 | Lab | `192.168.30.0/24` | Proxmox nodes and lab guests |

## Traffic Policy

| Source | Destination | Policy |
| --- | --- | --- |
| Management | All VLANs | Allow administration traffic |
| Production | Management | Deny new connections unless required |
| Lab | Production | Deny by default |
| Reverse proxy | Service backends | Allow required application ports |
| Prometheus | Exporters | Allow TCP 9100 |
| Tailscale clients | Internal networks | Allow according to access policy |

## Switch Port Example

| Port | Device | Mode | VLANs |
| --- | --- | --- | --- |
| 1 | Router uplink | Trunk | 1, 20, 30 |
| 2 | `ust-vault` | Access | 20 |
| 3 | `ust-axiom` | Access | 20 |
| 4 | `ust-overseer` | Access | 1 |
| 5 | `ust-sentinel-01` | Access | 30 |
| 6 | `ust-sentinel-02` | Access | 30 |
| 7 | `archlinux` | Access | 1 |


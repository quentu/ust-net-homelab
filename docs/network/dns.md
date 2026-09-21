# Internal DNS

Internal services use the `intra.quentu.dev` zone. Technitium DNS on `ust-overseer` provides local records, while Cloudflare manages the public `quentu.dev` domain.

## Host Records

| Record | Type | Value |
| --- | --- | --- |
| `ust-overseer.intra.quentu.dev` | A | `192.168.10.100` |
| `ust-axiom.intra.quentu.dev` | A | `192.168.20.108` |
| `ust-sentinel-01.intra.quentu.dev` | A | `192.168.30.100` |
| `ust-sentinel-02.intra.quentu.dev` | A | `192.168.30.101` |

## Service Records

Service records resolve to the reverse proxy rather than directly to application backends.

| Record | Type | Value |
| --- | --- | --- |
| `jellyfin.intra.quentu.dev` | A | `192.168.10.100` |
| `photos.intra.quentu.dev` | A | `192.168.10.100` |
| `grafana.intra.quentu.dev` | A | `192.168.10.100` |
| `pve.intra.quentu.dev` | A | `192.168.10.100` |

Tailscale clients use split DNS for `intra.quentu.dev`, allowing the same names to work locally and remotely.


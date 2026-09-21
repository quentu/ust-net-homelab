# ust-overseer

<p align="left">
  <img src="/home/quentu/Projects/ust-net-homelab/assets/img_02_overseer.png" alt="Homelab rack" width="300">
</p>

## Overview

`ust-overseer` is the management node for UST-NET. It provides remote access, internal DNS, HTTPS routing, monitoring, and the PyDash status display.

| Property | Value |
| --- | --- |
| Role | Management / Control |
| Network | VLAN 1 |
| Address | `192.168.10.100` |
| Platform | Intel NUC in custom "Cyberdeck" enclosure |
| Operating System | Debian Linux |

## Services

| Service | Purpose |
| --- | --- |
| Technitium DNS | Internal DNS for `intra.quentu.dev` |
| NGINX | HTTPS reverse proxy |
| Tailscale | Remote access and subnet routing |
| Prometheus | Metrics collection |
| Grafana | Monitoring dashboards |
| PyDash | CLI infrastructure dashboard |

## Monitoring

Prometheus scrapes exporters across the homelab. Example target:

```yaml
- job_name: "nodes"
  static_configs:
    - targets:
        - "192.168.20.108:9100"
      labels:
        host: "ust-axiom"
```

PyDash pulls metrics from server-agent.service (on hosts) Example target:

```yaml
- name: ust-axiom
  url: http://192.168.20.108:8000/stats
```

## Kiosk Session

PyDash runs from a dedicated `dashboard` user inside Alacritty and spectrwm. The account is separate from the normal administrative user, preventing unauthorized root access.

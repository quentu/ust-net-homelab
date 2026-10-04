# Remote Access

Tailscale provides private remote access without exposing management ports through Starlink.

## Subnet Router

`ust-overseer` advertises the internal subnets to the Tailscale network:

```text
192.168.10.0/24
192.168.20.0/24
192.168.30.0/24
```


Example route advertisement:

```bash
sudo tailscale up \
  --advertise-routes=192.168.10.0/24,192.168.20.0/24,192.168.30.0/24
```
## Exit Node
Devices that access networks outside the LAN are required to route their traffic through Mullvad VPN exit nodes.

Assigned devices:
- `arch-laptop`
- `iPhone`
## DNS

Split DNS sends queries for `intra.quentu.dev` to the internal DNS server on `ust-overseer`.

## Access Model

- Administration is limited to approved Tailscale users and devices.
- Internal web services remain behind the reverse proxy.
- A local console remains available if remote access is unavailable.


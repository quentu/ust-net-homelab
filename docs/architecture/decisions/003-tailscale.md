# ADR 003: Tailscale Remote Access

- **Status:** Accepted
- **Decision:** Use Tailscale for private remote access.

## Context

The Starlink connection uses CGNAT, preventing conventional inbound port forwarding. UST-NET still requires secure remote administration and access to private services.

## Decision

`ust-overseer` acts as a Tailscale subnet router for the management, production, and lab networks. Split DNS sends `intra.quentu.dev` queries to the internal DNS server.

## Consequences

- No public management ports are required.
- Authorized devices can reach internal services from outside the LAN.
- Access is controlled through Tailscale identity and policy.
- Routed access heavily depends on `ust-overseer` availability.


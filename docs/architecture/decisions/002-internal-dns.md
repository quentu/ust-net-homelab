# ADR 002: Internal DNS

- **Status:** Accepted
- **Decision:** Use `intra.quentu.dev` for private service discovery.

## Context

Applications need stable names that remain unchanged when a backend address or host changes. Direct IP access also makes HTTPS certificate management harder.

## Decision

Technitium DNS on `ust-overseer` serves the `intra.quentu.dev` zone. Service records resolve to the Nginx reverse proxy, which forwards traffic to the current backend.

Example:

```text
jellyfin.intra.quentu.dev → 192.168.10.100 (ust-overseer)
```


## Consequences

- Service names remain stable when workloads move.
- Local and Tailscale clients use the same addresses.
- Internal DNS and the reverse proxy become important dependencies.
- DNS records remain separate from access-control policy.


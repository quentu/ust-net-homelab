# ADR 001: VLAN Segmentation

- **Status:** Accepted
- **Decision:** Separate management, production, and lab workloads by VLAN.

## Context

UST-NET contains both stable production services and experimental virtual machines. A flat network would allow lab workloads to reach production and management systems unnecessarily.

## Decision

| VLAN | Purpose |
| --- | --- |
| 1 | Management |
| 20 | Production |
| 30 | Lab |

Inter-VLAN traffic is denied by default and allowed only when a service requires it. Management systems can administer hosts across all three networks.

## Consequences

- Lab changes are isolated from production services.
- Switch ports and Proxmox bridges require VLAN-aware configuration.
- Troubleshooting must consider both routing and firewall policy.


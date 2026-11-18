# ADR 004: Direct Power for ust-overseer

- **Status:** Accepted
- **Decision:** Replace the DIY 4S1P 18650 battery pack with direct power for `ust-overseer`.

## Context

`ust-overseer` was previously powered by a DIY 4S1P battery pack consisting of four 18650 lithium-ion cells. However, the battery pack proved unreliable and could not consistently provide sufficient power for stable operation. Since `ust-overseer` provides critical network services, reliable power delivery is necessary.

## Decision

Remove the 4S1P 18650 battery pack and power `ust-overseer` directly using an appropriate external power supply.

## Consequences

- Improved power stability and reliability.
- Eliminates power limitations associated with the DIY battery pack.
- Reduces maintenance and complexity of the power setup.
- `ust-overseer` will no longer have battery backup and will shut down during power outages until an external UPS is implemented.
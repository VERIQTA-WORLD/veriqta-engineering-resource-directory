# Chaos engineer: related careers

[Career overview](README.md) · [SRE and reliability directory](../README.md)

These collections overlap in reliability concerns but emphasize different engineering boundaries. Role ownership varies by organization; use the scope descriptions to find the resources you need.

## Adjacent resource collections

| Career | Distinct emphasis and overlap | Collection status |
| --- | --- | --- |
| [Resilience engineer](../resilience-engineer/README.md) | Resources for preserving useful service during faults and recovering after disruption. | Included in this folder. |
| [Reliability engineer](../reliability-engineer/README.md) | Resources for assessing and improving the dependability of software systems using explicit service outcomes, failure models, design reviews, tests, and production evidence. | Included in this folder. |
| [Site reliability engineer](../site-reliability-engineer/README.md) | Resources for applying engineering to service operations: service objectives, observability, on-call response, incident learning, safe changes, capacity, automation, and recovery. | Included in this folder. |
| [Capacity engineer](../capacity-engineer/README.md) | Resources for measuring demand, identifying bottlenecks, forecasting resource needs, and validating the capacity available during normal operation and failures. | Included in this folder. |
| [Cloud reliability engineer](../cloud-reliability-engineer/README.md) | Resources for operating reliable cloud workloads across provider health, service limits, identity, networking, scaling, deployment, persistent data, and regional recovery. | Included in this folder. |

## Shared references

These direct references remain useful when moving between the adjacent collections. Their inclusion does not make the roles interchangeable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |
| [Chaos Toolkit documentation](https://chaostoolkit.org/) | Explore experiment definitions, drivers, and execution guidance for hypothesis-based failure testing. | Advanced; public project documentation. Extensions need separate review; experiments can affect availability and data. |
| [Chaos Mesh documentation](https://chaos-mesh.org/docs/) | Find experiment types, scheduling, permissions, and fault-injection guidance. | Advanced; public project documentation. Cluster and node effects vary by experiment; define abort conditions and verify recovery. |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |

[Browse all 12 SRE and reliability careers](../README.md#career-collections)

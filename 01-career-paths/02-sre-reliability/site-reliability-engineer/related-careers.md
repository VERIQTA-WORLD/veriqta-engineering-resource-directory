# Site reliability engineer: related careers

[Career overview](README.md) · [SRE and reliability directory](../README.md)

These collections overlap in reliability concerns but emphasize different engineering boundaries. Role ownership varies by organization; use the scope descriptions to find the resources you need.

## Adjacent resource collections

| Career | Distinct emphasis and overlap | Collection status |
| --- | --- | --- |
| [Service reliability engineer](../service-reliability-engineer/README.md) | Resources for operating an individual service or connected service boundary: user-facing outcomes, dependencies, latency, correctness, change safety, capacity, and recovery. | Included in this folder. |
| [Platform reliability engineer](../platform-reliability-engineer/README.md) | Resources for keeping shared developer and runtime platforms dependable: provisioning, reconciliation, build and delivery services, artifact distribution, identity, telemetry, and recovery. | Included in this folder. |
| [Infrastructure reliability engineer](../infrastructure-reliability-engineer/README.md) | Resources for reliability of compute, hosts, provisioning, storage, networking, and infrastructure control systems. | Included in this folder. |
| [Cloud reliability engineer](../cloud-reliability-engineer/README.md) | Resources for operating reliable cloud workloads across provider health, service limits, identity, networking, scaling, deployment, persistent data, and regional recovery. | Included in this folder. |
| [Reliability engineer](../reliability-engineer/README.md) | Resources for assessing and improving the dependability of software systems using explicit service outcomes, failure models, design reviews, tests, and production evidence. | Included in this folder. |
| [Resilience engineer](../resilience-engineer/README.md) | Resources for preserving useful service during faults and recovering after disruption. | Included in this folder. |

## Shared references

These direct references remain useful when moving between the adjacent collections. Their inclusion does not make the roles interchangeable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Google SRE books](https://sre.google/books/) | Locate original reliability, operational, and secure-system engineering references. | Intermediate to advanced; examples reflect their authors' environments and publication periods. |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |

[Browse all 12 SRE and reliability careers](../README.md#career-collections)

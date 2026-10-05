# Service reliability engineer: related careers

[Career overview](README.md) · [SRE and reliability directory](../README.md)

These collections overlap in reliability concerns but emphasize different engineering boundaries. Role ownership varies by organization; use the scope descriptions to find the resources you need.

## Adjacent resource collections

| Career | Distinct emphasis and overlap | Collection status |
| --- | --- | --- |
| [Site reliability engineer](../site-reliability-engineer/README.md) | Resources for applying engineering to service operations: service objectives, observability, on-call response, incident learning, safe changes, capacity, automation, and recovery. | Included in this folder. |
| [Platform reliability engineer](../platform-reliability-engineer/README.md) | Resources for keeping shared developer and runtime platforms dependable: provisioning, reconciliation, build and delivery services, artifact distribution, identity, telemetry, and recovery. | Included in this folder. |
| [Database reliability engineer](../database-reliability-engineer/README.md) | Resources for database availability, correctness, durability, query performance, replication, maintenance, backup, and recovery. | Included in this folder. |
| [Network reliability engineer](../network-reliability-engineer/README.md) | Resources for reliable connectivity, routing, DNS, traffic distribution, service discovery, and network-dependent application behavior. | Included in this folder. |
| [Resilience engineer](../resilience-engineer/README.md) | Resources for preserving useful service during faults and recovering after disruption. | Included in this folder. |

## Shared references

These direct references remain useful when moving between the adjacent collections. Their inclusion does not make the roles interchangeable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |

[Browse all 12 SRE and reliability careers](../README.md#career-collections)

# Database reliability engineer: related careers

[Career overview](README.md) · [SRE and reliability directory](../README.md)

These collections overlap in reliability concerns but emphasize different engineering boundaries. Role ownership varies by organization; use the scope descriptions to find the resources you need.

## Adjacent resource collections

| Career | Distinct emphasis and overlap | Collection status |
| --- | --- | --- |
| [Service reliability engineer](../service-reliability-engineer/README.md) | Resources for operating an individual service or connected service boundary: user-facing outcomes, dependencies, latency, correctness, change safety, capacity, and recovery. | Included in this folder. |
| [Capacity engineer](../capacity-engineer/README.md) | Resources for measuring demand, identifying bottlenecks, forecasting resource needs, and validating the capacity available during normal operation and failures. | Included in this folder. |
| [Infrastructure reliability engineer](../infrastructure-reliability-engineer/README.md) | Resources for reliability of compute, hosts, provisioning, storage, networking, and infrastructure control systems. | Included in this folder. |
| [Resilience engineer](../resilience-engineer/README.md) | Resources for preserving useful service during faults and recovering after disruption. | Included in this folder. |
| [Site reliability engineer](../site-reliability-engineer/README.md) | Resources for applying engineering to service operations: service objectives, observability, on-call response, incident learning, safe changes, capacity, automation, and recovery. | Included in this folder. |

## Shared references

These direct references remain useful when moving between the adjacent collections. Their inclusion does not make the roles interchangeable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [PostgreSQL explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html) | Understand lock conflicts and deadlock behavior before intervening in blocked database work. | Intermediate; public reference. Terminating a session can abort transactions and affect application behavior. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Find the author's book information and supporting resources for data-system design. | Intermediate to advanced; public book website. Full books are separate purchases; choose an edition and check publication details. |

[Browse all 12 SRE and reliability careers](../README.md#career-collections)

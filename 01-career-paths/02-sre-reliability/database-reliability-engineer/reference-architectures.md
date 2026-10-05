# Database reliability engineer: reference architectures and design guidance

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

## Browse this page

- [Data consistency and availability models](#data-consistency-and-availability-models)
- [Application and database dependency behavior](#application-and-database-dependency-behavior)
- [Recovery and documented decisions](#recovery-and-documented-decisions)

## Data consistency and availability models

Review the database model and tested version before selecting replication or failover. Replica counts do not settle correctness or recovery behavior.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [Patroni documentation](https://patroni.readthedocs.io/en/latest/) | Compare PostgreSQL high-availability orchestration and its distributed coordination dependencies. | Advanced; public project reference. Review fencing, datastore behavior, failover policy, and recovery; an orchestrator is not a backup. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Jepsen analyses](https://jepsen.io/analyses) | Read independent system-consistency investigations and their tested assumptions. | Advanced; public research collection. Findings are tied to tested versions and scenarios; do not transfer a historical verdict to every later release. |
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Find the author's book information and supporting resources for data-system design. | Intermediate to advanced; public book website. Full books are separate purchases; choose an edition and check publication details. |

## Application and database dependency behavior

Plan pooling, retry, timeout, overload, and reconnection together. A database failover can succeed while the application remains unable to complete work.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PgBouncer documentation](https://www.pgbouncer.org/config.html) | Compare connection pooling behavior, resource settings, and application compatibility. | Intermediate; public configuration reference. Pooling mode and session-dependent application features affect correctness. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [Azure circuit breaker pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker) | Compare dependency-failure containment and recovery-probe behavior. | Intermediate; public pattern. Thresholds and reset behavior must match the dependency and user impact. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Data processing pipelines](https://sre.google/workbook/data-processing/) | Study reliability concerns in scheduled and streaming processing, including timeliness and completion. | Intermediate to advanced; public chapter. User-facing correctness and freshness may matter more than process uptime. |

## Recovery and documented decisions

Record acceptable data loss, recovery time, archive and credential dependencies, verification, and the owner of restored data acceptance.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Advanced; test identity, configuration, data, and traffic restoration together. |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |
| [SLO engineering case studies](https://sre.google/workbook/slo-engineering-case-studies/) | Compare service-objective decisions and measurement approaches in concrete cases. | Intermediate; public chapter. Keep the service boundary and user expectations explicit. |

[Browse the other collections](README.md#resource-collections)

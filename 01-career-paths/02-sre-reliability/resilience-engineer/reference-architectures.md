# Resilience engineer: reference architectures and design guidance

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

## Browse this page

- [Keep serving through dependency failure](#keep-serving-through-dependency-failure)
- [Recover data and infrastructure](#recover-data-and-infrastructure)
- [Review designs and experiments](#review-designs-and-experiments)

## Keep serving through dependency failure

Study static stability, workload isolation, and degraded service patterns. Write down which requests remain supported and which dependencies are still indispensable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [AWS Builders' Library: workload isolation](https://d1.awsstatic.com/builderslibrary/pdfs/workload-isolation-using-shuffle-sharding.pdf) | Explore isolation patterns for limiting correlated impact across tenants and workloads. | Advanced; public original engineering article in PDF. Historical design account; adapt failure domains and assumptions to the actual workload. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Azure circuit breaker pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker) | Compare dependency-failure containment and recovery-probe behavior. | Intermediate; public pattern. Thresholds and reset behavior must match the dependency and user impact. |
| [Azure deployment stamps pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/deployment-stamp) | Compare independently deployable workload units and their failure boundaries. | Advanced; public pattern. Routing, data ownership, and stamp-level capacity affect recovery and operational complexity. |
| [Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/) | Compare patterns addressing distributed-system concerns and trade-offs. | Intermediate; examples are provider-oriented, while many problem statements apply more broadly. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |

## Recover data and infrastructure

Compare recovery objectives, backup material, infrastructure reconstruction, and provider-specific dependencies. Multi-region deployment alone does not prove disaster recovery.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Advanced; test identity, configuration, data, and traffic restoration together. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Advanced; use documentation matching the deployed database version and test restored data. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |

## Review designs and experiments

Connect risk assumptions to a testable hypothesis, observed service behavior, and a decision record. Provider review frameworks cover more than availability.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |
| [AWS Well-Architected reliability pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | Review reliability questions for cloud workload foundations, change, and recovery. | Intermediate; public provider framework. Review actual service limits and workload evidence; framework use is not certification. |
| [Azure Well-Architected reliability guidance](https://learn.microsoft.com/en-us/azure/well-architected/reliability/) | Find provider guidance for failure analysis, redundancy, recovery, and reliability review. | Intermediate; public framework. Apply to the deployed services and their documented responsibility boundaries. |
| [Google Cloud reliability framework](https://cloud.google.com/architecture/framework/reliability) | Review workload reliability principles and provider-specific design considerations. | Intermediate; public framework. Architecture guidance does not guarantee that every managed service meets your objective. |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review workload decisions across operational, reliability, security, performance, cost, and sustainability concerns. | Intermediate to advanced; AWS-specific guidance. Adapt recommendations to requirements. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Review Azure workload architecture and quality trade-offs. | Intermediate to advanced; assess workload context rather than treating guidance as a universal checklist. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Review Google Cloud architecture guidance across its documented pillars. | Intermediate to advanced; provider-specific capabilities and assumptions need review. |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |

[Browse the other collections](README.md#resource-collections)

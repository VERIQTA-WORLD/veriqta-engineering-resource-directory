# Service reliability engineer: reference architectures and design guidance

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

## Browse this page

- [Boundaries, dependency control, and useful degradation](#boundaries-dependency-control-and-useful-degradation)
- [Release, configuration, and operational ownership](#release-configuration-and-operational-ownership)
- [State, provider architecture, and recovery](#state-provider-architecture-and-recovery)

## Boundaries, dependency control, and useful degradation

Compare design patterns around the actual service contract. Identify which outcomes remain supported when a dependency, location, or capacity source fails.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [The Twelve-Factor App](https://12factor.net/) | Review application configuration, deployment, and operability principles. | Foundation to intermediate; useful design guidance, not a complete security or resilience architecture. |
| [Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/) | Compare patterns addressing distributed-system concerns and trade-offs. | Intermediate; examples are provider-oriented, while many problem statements apply more broadly. |
| [Azure circuit breaker pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker) | Compare dependency-failure containment and recovery-probe behavior. | Intermediate; public pattern. Thresholds and reset behavior must match the dependency and user impact. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [AWS Builders' Library: workload isolation](https://d1.awsstatic.com/builderslibrary/pdfs/workload-isolation-using-shuffle-sharding.pdf) | Explore isolation patterns for limiting correlated impact across tenants and workloads. | Advanced; public original engineering article in PDF. Historical design account; adapt failure domains and assumptions to the actual workload. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |

## Release, configuration, and operational ownership

Connect design and release controls to an operating agreement. Document the service boundary, owners, changes, and decisions that affect reliability.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Reliable product launches](https://sre.google/sre-book/reliable-product-launches/) | Compare readiness review, launch coordination, and production-risk reduction. | Intermediate; public book chapter. Select checks appropriate to the service and the people who own it. |
| [The evolving SRE engagement model](https://sre.google/workbook/engagement-model/) | Understand service engagement, collaboration, and operational responsibility boundaries. | Intermediate; public workbook chapter. Organizational labels and staffing models vary; explicitly agree ownership locally. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |
| [Configuration design and best practices](https://sre.google/workbook/configuration-design/) | Review interfaces, validation, and change control for configuration-driven systems. | Intermediate; public chapter. Syntax validation alone cannot establish a safe operational change. |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |
| [Team Topologies resources](https://teamtopologies.com/) | Explore the authors' model for team boundaries and interaction modes. | Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions. |

## State, provider architecture, and recovery

Review consistency and recovery assumptions alongside the provider architecture. A service-level recovery plan must cover its external dependencies and stored state.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Advanced; use documentation matching the deployed database version and test restored data. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Advanced; test identity, configuration, data, and traffic restoration together. |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Intermediate to advanced; filter by your workload and operational constraints. |

[Browse the other collections](README.md#resource-collections)

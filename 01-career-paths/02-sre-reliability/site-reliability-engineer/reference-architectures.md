# Site reliability engineer: reference architectures and design guidance

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

## Browse this page

- [Ownership and production readiness](#ownership-and-production-readiness)
- [Dependency failure, overload, and recovery](#dependency-failure-overload-and-recovery)
- [Provider and delivery review](#provider-and-delivery-review)

## Ownership and production readiness

Use engagement, launch, configuration, and platform guidance to establish service boundaries and an operating agreement. Job titles alone do not establish responsibility.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [The evolving SRE engagement model](https://sre.google/workbook/engagement-model/) | Understand service engagement, collaboration, and operational responsibility boundaries. | Intermediate; public workbook chapter. Organizational labels and staffing models vary; explicitly agree ownership locally. |
| [Reliable product launches](https://sre.google/sre-book/reliable-product-launches/) | Compare readiness review, launch coordination, and production-risk reduction. | Intermediate; public book chapter. Select checks appropriate to the service and the people who own it. |
| [Configuration design and best practices](https://sre.google/workbook/configuration-design/) | Review interfaces, validation, and change control for configuration-driven systems. | Intermediate; public chapter. Syntax validation alone cannot establish a safe operational change. |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Intermediate; platform design must start with developer and operator needs. |
| [Team Topologies resources](https://teamtopologies.com/) | Explore the authors' model for team boundaries and interaction modes. | Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions. |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |

## Dependency failure, overload, and recovery

Compare failure containment, retries, static stability, state integrity, and disaster-recovery designs against the actual workload.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Azure circuit breaker pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker) | Compare dependency-failure containment and recovery-probe behavior. | Intermediate; public pattern. Thresholds and reset behavior must match the dependency and user impact. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Advanced; test identity, configuration, data, and traffic restoration together. |

## Provider and delivery review

Select the provider architecture and release practices relevant to the service. Record assumptions and evidence for readiness, changes, and recovery rather than simply copying a blueprint.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Intermediate to advanced; filter by your workload and operational constraints. |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review workload decisions across operational, reliability, security, performance, cost, and sustainability concerns. | Intermediate to advanced; AWS-specific guidance. Adapt recommendations to requirements. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Review Azure workload architecture and quality trade-offs. | Intermediate to advanced; assess workload context rather than treating guidance as a universal checklist. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Review Google Cloud architecture guidance across its documented pillars. | Intermediate to advanced; provider-specific capabilities and assumptions need review. |
| [Release engineering](https://sre.google/sre-book/release-engineering/) | Study an original account of build, release, and deployment engineering. | Intermediate to advanced; Google-specific practices require adaptation. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Advanced; official PDF. Application and schema compatibility must be tested in your own system. |

[Browse the other collections](README.md#resource-collections)

# DevOps consultant: reference architectures and design guidance

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Cloud and platform designs

Record workload, tenancy, availability, and skills assumptions before selecting a design. Reference architectures are comparison material, not automatic approval of a migration.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Public reference. Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Public reference. Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Public reference. Intermediate to advanced; filter by your workload and operational constraints. |
| [Amazon EKS best practices](https://docs.aws.amazon.com/eks/latest/best-practices/introduction.html) | Review Kubernetes workload and cluster-design guidance for EKS. | Public reference. Advanced; EKS-specific assumptions must be separated from general Kubernetes advice. |
| [AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks) | Examine a documented infrastructure baseline for an Azure Kubernetes Service cluster. | Public reference. Advanced; adapt identity, network, availability, and cost choices to requirements. |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Public reference. Intermediate; platform design must start with developer and operator needs. |

## Patterns and decision records

Use patterns to evaluate a specific failure or coupling problem. Keep an architecture decision record with alternatives, consequences, and the evidence needed to revisit it.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Public reference. Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Public reference. Foundation onward; keep decisions connected to evidence and later changes. |
| [Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/) | Compare patterns addressing distributed-system concerns and trade-offs. | Public reference. Intermediate; examples are provider-oriented, while many problem statements apply more broadly. |
| [The Twelve-Factor App](https://12factor.net/) | Review application configuration, deployment, and operability principles. | Public reference. Foundation to intermediate; useful design guidance, not a complete security or resilience architecture. |
| [Team Topologies resources](https://teamtopologies.com/) | Explore the authors' model for team boundaries and interaction modes. | Public reference. Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions. |
| [Non-abstract large system design](https://sre.google/workbook/non-abstract-design/) | Connect system design to concrete capacity, dependency, and failure assumptions. | Advanced; public workbook chapter. Recalculate workload assumptions rather than reusing example capacity figures. |

## Change, retry, and recovery assumptions

Test compatibility, duplicate requests, dependency failures, and recovery claims before promising an outcome.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Public reference. Advanced; official PDF. Application and schema compatibility must be tested in your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Public reference. Advanced; operation semantics determine which retry behavior is safe. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Public reference. Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Public reference. Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Public reference. Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Public reference. Advanced; test identity, configuration, data, and traffic restoration together. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

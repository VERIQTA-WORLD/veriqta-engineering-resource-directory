# DevOps platform engineer: reference architectures and design guidance

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Platform purpose and operating model

Start with capabilities, users, and responsibility boundaries before choosing products. Platform maturity guidance and engagement examples help frame review questions.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Public reference. Intermediate; platform design must start with developer and operator needs. |
| [CNCF platform engineering maturity model](https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/) | Evaluate platform capabilities and improvement dimensions beyond the existence of a developer portal. | Intermediate; public community framework. A maturity model supports discussion; it does not certify a platform or prescribe one product stack. |
| [Team Topologies resources](https://teamtopologies.com/) | Explore the authors' model for team boundaries and interaction modes. | Public reference. Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions. |
| [The evolving SRE engagement model](https://sre.google/workbook/engagement-model/) | Understand service engagement, collaboration, and operational responsibility boundaries. | Intermediate; public workbook chapter. Organizational labels and staffing models vary; explicitly agree ownership locally. |

## Cloud and Kubernetes platform designs

Review tenancy, network, identity, node, control-plane, and supporting-service assumptions before adapting a baseline. Managed services change responsibilities, not all risks.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon EKS best practices](https://docs.aws.amazon.com/eks/latest/best-practices/introduction.html) | Review Kubernetes workload and cluster-design guidance for EKS. | Public reference. Advanced; EKS-specific assumptions must be separated from general Kubernetes advice. |
| [AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks) | Examine a documented infrastructure baseline for an Azure Kubernetes Service cluster. | Public reference. Advanced; adapt identity, network, availability, and cost choices to requirements. |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Public reference. Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Public reference. Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Public reference. Intermediate to advanced; filter by your workload and operational constraints. |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Public reference. Advanced; namespaces alone do not provide every required isolation boundary. |

## Interfaces, reconciliation, and change decisions

Document how user requests become controlled changes and how their outcomes are observed. Keep artifact trust, deployment reconciliation, and rollout decisions distinct.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Public reference. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |
| [Backstage software templates](https://backstage.io/docs/features/software-templates/) | Design scaffolding interfaces for repeatable developer workflows. | Intermediate; public project documentation. Template actions execute with configured credentials; validate inputs and review privileged integrations. |
| [Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/) | Compare patterns addressing distributed-system concerns and trade-offs. | Public reference. Intermediate; examples are provider-oriented, while many problem statements apply more broadly. |
| [OpenGitOps principles](https://opengitops.dev/) | Use shared principles to discuss declarative state, version history, pull, and reconciliation. | Public reference. Intermediate; community principles. Evaluate whether the implementation meets them. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Public reference. Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Public reference. Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Public reference. Foundation onward; keep decisions connected to evidence and later changes. |

## Service reliability and dependency behavior

Treat platform dependencies and execution queues as sources of failures affecting many teams. Review retry load and recovery of the platform’s own state.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Public reference. Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Public reference. Advanced; operation semantics determine which retry behavior is safe. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Public reference. Advanced; validate containment strategies with bounded tests and measurements. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Public reference. Advanced; official PDF. Application and schema compatibility must be tested in your own system. |
| [Non-abstract large system design](https://sre.google/workbook/non-abstract-design/) | Connect system design to concrete capacity, dependency, and failure assumptions. | Advanced; public workbook chapter. Recalculate workload assumptions rather than reusing example capacity figures. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

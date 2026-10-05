# DevOps infrastructure engineer: reference architectures and design guidance

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Cloud foundations and infrastructure review

Use these as concrete design references for tenancy, identity, network organization, and workload operation. Recalculate assumptions for the actual estate.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Public reference. Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Public reference. Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Public reference. Intermediate to advanced; filter by your workload and operational constraints. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Public reference. Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Public reference. Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review workload decisions across operational, reliability, security, performance, cost, and sustainability concerns. | Public reference. Intermediate to advanced; AWS-specific guidance. Adapt recommendations to requirements. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Review Azure workload architecture and quality trade-offs. | Public reference. Intermediate to advanced; assess workload context rather than treating guidance as a universal checklist. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Review Google Cloud architecture guidance across its documented pillars. | Public reference. Intermediate to advanced; provider-specific capabilities and assumptions need review. |

## Container and platform infrastructure

Evaluate node and control-plane ownership, operational dependencies, availability targets, and resource isolation before adopting a reference design.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon EKS best practices](https://docs.aws.amazon.com/eks/latest/best-practices/introduction.html) | Review Kubernetes workload and cluster-design guidance for EKS. | Public reference. Advanced; EKS-specific assumptions must be separated from general Kubernetes advice. |
| [AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks) | Examine a documented infrastructure baseline for an Azure Kubernetes Service cluster. | Public reference. Advanced; adapt identity, network, availability, and cost choices to requirements. |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Public reference. Intermediate; platform design must start with developer and operator needs. |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Public reference. Advanced; namespaces alone do not provide every required isolation boundary. |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Public reference. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |

## Recovery and documented decisions

Specify which infrastructure, state, images, secrets, and data must be recoverable together. Record alternative designs and the evidence behind recovery targets.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Public reference. Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Public reference. Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Public reference. Advanced; test identity, configuration, data, and traffic restoration together. |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Public reference. Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Public reference. Foundation onward; keep decisions connected to evidence and later changes. |
| [Non-abstract large system design](https://sre.google/workbook/non-abstract-design/) | Connect system design to concrete capacity, dependency, and failure assumptions. | Advanced; public workbook chapter. Recalculate workload assumptions rather than reusing example capacity figures. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

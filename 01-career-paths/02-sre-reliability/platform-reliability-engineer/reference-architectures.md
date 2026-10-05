# Platform reliability engineer: reference architectures and design guidance

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

## Browse this page

- [Platform scope and operating model](#platform-scope-and-operating-model)
- [Isolation and failure containment](#isolation-and-failure-containment)
- [Provider blueprints and decision records](#provider-blueprints-and-decision-records)

## Platform scope and operating model

Use these references to define platform users, service boundaries, ownership, and adoption. Maturity models describe practices; they do not guarantee availability.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Intermediate; platform design must start with developer and operator needs. |
| [CNCF platform engineering maturity model](https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/) | Evaluate platform capabilities and improvement dimensions beyond the existence of a developer portal. | Intermediate; public community framework. A maturity model supports discussion; it does not certify a platform or prescribe one product stack. |
| [Backstage software catalog](https://backstage.io/docs/features/software-catalog/) | Model service ownership and metadata discovery for a developer portal. | Intermediate; public documentation. Catalog metadata is not proof that a service meets production controls. |
| [Team Topologies resources](https://teamtopologies.com/) | Explore the authors' model for team boundaries and interaction modes. | Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions. |
| [The evolving SRE engagement model](https://sre.google/workbook/engagement-model/) | Understand service engagement, collaboration, and operational responsibility boundaries. | Intermediate; public workbook chapter. Organizational labels and staffing models vary; explicitly agree ownership locally. |
| [Reliable product launches](https://sre.google/sre-book/reliable-product-launches/) | Compare readiness review, launch coordination, and production-risk reduction. | Intermediate; public book chapter. Select checks appropriate to the service and the people who own it. |

## Isolation and failure containment

Compare control-plane dependence, tenant boundaries, recovery, and shared failure domains before selecting a deployment pattern.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Advanced; namespaces alone do not provide every required isolation boundary. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Azure deployment stamps pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/deployment-stamp) | Compare independently deployable workload units and their failure boundaries. | Advanced; public pattern. Routing, data ownership, and stamp-level capacity affect recovery and operational complexity. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [AWS Builders' Library: workload isolation](https://d1.awsstatic.com/builderslibrary/pdfs/workload-isolation-using-shuffle-sharding.pdf) | Explore isolation patterns for limiting correlated impact across tenants and workloads. | Advanced; public original engineering article in PDF. Historical design account; adapt failure domains and assumptions to the actual workload. |
| [Amazon EKS best practices](https://docs.aws.amazon.com/eks/latest/best-practices/introduction.html) | Review Kubernetes workload and cluster-design guidance for EKS. | Advanced; EKS-specific assumptions must be separated from general Kubernetes advice. |
| [AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks) | Examine a documented infrastructure baseline for an Azure Kubernetes Service cluster. | Advanced; adapt identity, network, availability, and cost choices to requirements. |

## Provider blueprints and decision records

Select a blueprint for the actual provider and constraints, then record deviations and evidence. Organization foundations are substantial implementations rather than small local labs.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Intermediate to advanced; filter by your workload and operational constraints. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |

[Browse the other collections](README.md#resource-collections)

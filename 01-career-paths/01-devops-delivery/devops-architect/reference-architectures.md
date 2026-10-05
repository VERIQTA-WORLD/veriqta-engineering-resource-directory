# Reference architectures and design resources

Resources for comparing delivery-system, cloud-foundation, and platform designs. Read an architecture with its assumptions: workload, scale, identity, tenancy, availability, operating team, dependencies, and cost.

For an implementation to inspect or deploy in a sandbox, use [labs and projects](labs-and-projects.md). For control and protocol requirements, use [standards and frameworks](standards-and-frameworks.md).

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

## Cloud and platform reference architectures

Start with requirements, constraints, failure tolerance, and an operating model. These resources provide patterns to assess, not designs to copy without review.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Intermediate to advanced; filter by your workload and operational constraints. |
| [Amazon EKS best practices](https://docs.aws.amazon.com/eks/latest/best-practices/introduction.html) | Review Kubernetes workload and cluster-design guidance for EKS. | Advanced; EKS-specific assumptions must be separated from general Kubernetes advice. |
| [AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks) | Examine a documented infrastructure baseline for an Azure Kubernetes Service cluster. | Advanced; adapt identity, network, availability, and cost choices to requirements. |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Intermediate; platform design must start with developer and operator needs. |

## Design patterns and architecture communication

Use these references to make decisions reviewable. Record context, rejected options, consequences, and conditions that would change the decision.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |
| [Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/) | Compare patterns addressing distributed-system concerns and trade-offs. | Intermediate; examples are provider-oriented, while many problem statements apply more broadly. |
| [The Twelve-Factor App](https://12factor.net/) | Review application configuration, deployment, and operability principles. | Foundation to intermediate; useful design guidance, not a complete security or resilience architecture. |
| [Team Topologies resources](https://teamtopologies.com/) | Explore the authors' model for team boundaries and interaction modes. | Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions. |

---

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

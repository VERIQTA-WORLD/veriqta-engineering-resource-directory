# DevOps architect resource directory

Resources for designing how software is built, verified, released, operated, and recovered. A DevOps architect connects delivery workflows, infrastructure, platform capabilities, security controls, and operational ownership into a coherent system.

This directory helps you find references and compare options. It does not prescribe one toolchain or a training sequence. Use the collection that matches your current decision or problem.

## Browse the collection

| Collection | What you will find |
| --- | --- |
| [Toolkit](toolkit.md) | Tools grouped by capability, with official destinations and practical selection notes. |
| [Official documentation](official-documentation.md) | Focused delivery, infrastructure, Kubernetes, identity, and cloud references. |
| [Reference architectures](reference-architectures.md) | Cloud and platform designs, distributed-system patterns, and architecture-recording resources. |
| [Learning resources](learning-resources.md) | Books, research, tutorials, training catalogs, talks, and discovery collections. |
| [Labs and projects](labs-and-projects.md) | Workshops, local environments, demonstrations, and implementation repositories. |
| [Production responsibilities](production-responsibilities.md) | Operational references for release safety, service objectives, incidents, failure containment, recovery, security, and cost. |
| [Standards and frameworks](standards-and-frameworks.md) | Delivery principles, supply-chain requirements, security frameworks, and protocol specifications. |
| [Related careers](related-careers.md) | Adjacent roles, their overlap with architectural work, and relevant collections. |

## Find resources by the decision you need to make

| Your question | Start here | Continue with |
| --- | --- | --- |
| How should builds and releases execute? | [Pipeline tools](toolkit.md#source-control-and-delivery-pipelines) | [Delivery controls](official-documentation.md#delivery-systems-and-infrastructure-controls) |
| How should infrastructure changes be managed? | [Infrastructure automation](toolkit.md#infrastructure-and-configuration-automation) | [State and testing references](official-documentation.md#delivery-systems-and-infrastructure-controls) |
| Which platform and tenancy model fits? | [Architecture references](reference-architectures.md#cloud-and-platform-reference-architectures) | [Kubernetes tenancy and security](official-documentation.md#kubernetes-tenancy-workloads-and-security) |
| How should deployments be promoted and evaluated? | [GitOps and rollout tools](toolkit.md#gitops-and-progressive-delivery) | [Release-safety references](production-responsibilities.md#delivery-safety-and-control-plane-ownership) |
| How do we protect artifacts and delivery credentials? | [Supply-chain tools](toolkit.md#artifacts-and-software-supply-chain-tooling) | [Supply-chain references](standards-and-frameworks.md#delivery-and-software-supply-chain-references) |
| How do we observe and contain failures? | [Observability tools](toolkit.md#observability-and-diagnostics) | [Reliability and dependency references](production-responsibilities.md) |
| How do we demonstrate recovery and control cost? | [Recovery and economic references](production-responsibilities.md#recovery-security-cost-and-evidence) | [Resilience tools](toolkit.md#resilience-performance-and-recovery) |
| How can we explore an option safely? | [Labs and projects](labs-and-projects.md) | [Documentation](official-documentation.md) for the exact components involved |

## How to use an entry

The descriptions explain what a resource is useful for and the knowledge it assumes. Selection notes identify boundaries such as provider dependence, account requirements, operating burden, and historical context.

Start with official documentation when checking product behavior. Use architecture guidance and original engineering accounts to compare trade-offs. Use a sandbox implementation to investigate the chosen design; an example working once does not prove production readiness.

Public documentation is generally readable at its destination. Deploying the software or following an exercise may require paid services, accounts, permissions, and substantial machine resources. Course and book access conditions are called out separately.

Tool links go directly to official resources while the repository's canonical catalog is being developed. These career annotations describe architectural relevance; they are not competing canonical tool records.

## Repository navigation

- [Start here](../../../00-start-here/README.md)
- [All career paths](../../README.md)
- [Tools](../../../02-tools/README.md)
- [Technical domains](../../../03-technical-domains/README.md)
- [Cloud providers](../../../04-cloud-providers/README.md)
- [Technology ecosystems](../../../05-technology-ecosystems/README.md)
- [Production problems](../../../06-production-problems/README.md)

Some neighboring collections are still being developed. Their presence in the repository does not establish that their content has been reviewed.

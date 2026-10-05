# Cloud reliability engineer

[SRE and reliability directory](../README.md)

Resources for operating reliable cloud workloads across provider health, service limits, identity, networking, scaling, deployment, persistent data, and regional recovery. The collection separates provider responsibility from workload responsibility and connects architecture promises to measured user outcomes and exercised recovery.

## Find a resource

Use the collections below for the task in front of you. Compare purpose, prerequisites, deployment model, and operating limitations before choosing a tool or applying a guide. The tools are alternatives or complementary components, not a required stack.

## Resource collections

| Collection | What you will find |
| --- | --- |
| [Tool directory](toolkit.md) | Tools grouped by implementation or operating task, with alternatives and selection notes. |
| [Official documentation](official-documentation.md) | Authoritative manuals, API references, and focused operating guides. |
| [Reference architectures and design guidance](reference-architectures.md) | Documented designs, patterns, assumptions, and decision resources. |
| [Learning resources](learning-resources.md) | Books, tutorials, research, talks, and discovery collections by topic. |
| [Labs, examples, and projects](labs-and-projects.md) | Practice environments, examples, workshops, and implementation repositories. |
| [Production responsibilities and operational resources](production-responsibilities.md) | Operating concerns connected to diagnostic, incident, and recovery resources. |
| [Standards and frameworks](standards-and-frameworks.md) | Specifications, security guidance, and review frameworks with scope distinctions. |
| [Related careers](related-careers.md) | Adjacent collections, their overlap, and their development status. |

## Useful starting points

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Well-Architected reliability pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | Review reliability questions for cloud workload foundations, change, and recovery. | Intermediate; public provider framework. Review actual service limits and workload evidence; framework use is not certification. |
| [Azure Well-Architected reliability guidance](https://learn.microsoft.com/en-us/azure/well-architected/reliability/) | Find provider guidance for failure analysis, redundancy, recovery, and reliability review. | Intermediate; public framework. Apply to the deployed services and their documented responsibility boundaries. |
| [Google Cloud reliability framework](https://cloud.google.com/architecture/framework/reliability) | Review workload reliability principles and provider-specific design considerations. | Intermediate; public framework. Architecture guidance does not guarantee that every managed service meets your objective. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |

## Coverage

- Provider health and workload symptoms.
- Failure domains and shared responsibilities.
- Quotas, scaling and capacity.
- Cloud identity, networking and deployment.
- Managed and self-operated data recovery.
- Regional recovery and dependency behavior.
- Cost, service objectives and incident evidence.

## Reading and access

Foundation material assumes limited topic experience; intermediate material usually assumes basic implementation knowledge; advanced material often assumes practical systems or production experience. Each entry narrows those expectations where needed. Publicly readable instructions do not make a hosted service, commercial book, software license, or cloud experiment free.

Resource descriptions and destinations were reviewed on **5 October 2026**. Version, preview, development, and historical notes identify material that needs particular care. The linked manuals and collections are not claimed to have been read or tested in full. External links are used while repository resource IDs and canonical mappings remain unassigned.

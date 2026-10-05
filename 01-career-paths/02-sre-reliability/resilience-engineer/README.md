# Resilience engineer

[SRE and reliability directory](../README.md)

Resources for preserving useful service during faults and recovering after disruption. The collection emphasizes dependency isolation, degraded operation, overload control, recovery paths, disaster recovery, state protection, and experiments that test the assumptions behind a resilience design.

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
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |

## Coverage

- Failure domains and blast radius.
- Static stability and degraded operation.
- Timeouts, retries and dependency isolation.
- Recovery objectives and data loss.
- Backup, restore and failover.
- Controlled fault verification.
- Recovery ownership and incident learning.

## Reading and access

Foundation material assumes limited topic experience; intermediate material usually assumes basic implementation knowledge; advanced material often assumes practical systems or production experience. Each entry narrows those expectations where needed. Publicly readable instructions do not make a hosted service, commercial book, software license, or cloud experiment free.

Resource descriptions and destinations were reviewed on **5 October 2026**. Version, preview, development, and historical notes identify material that needs particular care. The linked manuals and collections are not claimed to have been read or tested in full. External links are used while repository resource IDs and canonical mappings remain unassigned.

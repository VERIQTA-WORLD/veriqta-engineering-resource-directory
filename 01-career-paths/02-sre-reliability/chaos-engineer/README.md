# Chaos engineer

[SRE and reliability directory](../README.md)

Resources for designing controlled failure experiments, collecting steady-state evidence, limiting blast radius, and validating recovery. The collection includes network and resource faults, Kubernetes and cloud experiments, dependency behavior, observability, data safety, and the operating agreement required before a test runs.

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
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |
| [Chaos Toolkit documentation](https://chaostoolkit.org/) | Explore experiment definitions, drivers, and execution guidance for hypothesis-based failure testing. | Advanced; public project documentation. Extensions need separate review; experiments can affect availability and data. |
| [Chaos Mesh documentation](https://chaos-mesh.org/docs/) | Find experiment types, scheduling, permissions, and fault-injection guidance. | Advanced; public project documentation. Cluster and node effects vary by experiment; define abort conditions and verify recovery. |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |

## Coverage

- Hypotheses and steady state.
- Experiment scope, authority and abort conditions.
- Network, resource and dependency faults.
- Platform and provider failure injection.
- Data protection and cleanup.
- Recovery and degraded behavior.
- Evidence, repeatability and incident learning.

## Reading and access

Foundation material assumes limited topic experience; intermediate material usually assumes basic implementation knowledge; advanced material often assumes practical systems or production experience. Each entry narrows those expectations where needed. Publicly readable instructions do not make a hosted service, commercial book, software license, or cloud experiment free.

Resource descriptions and destinations were reviewed on **5 October 2026**. Version, preview, development, and historical notes identify material that needs particular care. The linked manuals and collections are not claimed to have been read or tested in full. External links are used while repository resource IDs and canonical mappings remain unassigned.

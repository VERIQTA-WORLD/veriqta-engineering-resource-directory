# Service reliability engineer

[SRE and reliability directory](../README.md)

Resources for operating an individual service or connected service boundary: user-facing outcomes, dependencies, latency, correctness, change safety, capacity, and recovery. The collection connects instrumentation and alerting to API behavior, data dependencies, release controls, incident diagnosis, and practical verification.

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
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |

## Coverage

- Service boundaries and user journeys.
- SLIs, SLOs and actionable alerts.
- Dependency behavior and correctness.
- Safe release and configuration.
- Capacity and overload handling.
- Incident diagnosis and recovery.
- Operational ownership and improvement.

## Reading and access

Foundation material assumes limited topic experience; intermediate material usually assumes basic implementation knowledge; advanced material often assumes practical systems or production experience. Each entry narrows those expectations where needed. Publicly readable instructions do not make a hosted service, commercial book, software license, or cloud experiment free.

Resource descriptions and destinations were reviewed on **5 October 2026**. Version, preview, development, and historical notes identify material that needs particular care. The linked manuals and collections are not claimed to have been read or tested in full. External links are used while repository resource IDs and canonical mappings remain unassigned.

# Service reliability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Service reliability and operating practice](#service-reliability-and-operating-practice)
- [Dependencies, testing, and secure delivery](#dependencies-testing-and-secure-delivery)
- [Implementation tutorials and improvement evidence](#implementation-tutorials-and-improvement-evidence)
- [Foundation-level SRE training](#foundation-level-sre-training)

## Service reliability and operating practice

Use focused chapters and free book material to understand objectives, alerts, ownership, releases, and diagnosis. Examples require adaptation to local constraints.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [SLO engineering case studies](https://sre.google/workbook/slo-engineering-case-studies/) | Compare service-objective decisions and measurement approaches in concrete cases. | Intermediate; public chapter. Keep the service boundary and user expectations explicit. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Being on-call](https://sre.google/sre-book/being-on-call/) | Review escalation, operating preparedness, and the human responsibilities of incident coverage. | Foundation onward; public chapter. Staffing and escalation arrangements must be agreed locally. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |

## Dependencies, testing, and secure delivery

Use failure, load, integrity, and secure-delivery material to review the actual service contract and threat model.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html) | Explore security and reliability together in system design and operations. | Advanced; openly readable. Examples require interpretation for your environment. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Find the author's book information and supporting resources for data-system design. | Intermediate to advanced; public book website. Full books are separate purchases; choose an edition and check publication details. |

## Implementation tutorials and improvement evidence

Choose tutorials matching the implementation and use delivery research to investigate improvement opportunities. Broad community collections need their own item-level review.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes tutorials](https://kubernetes.io/docs/tutorials/) | Study official walkthroughs for workloads, services, configuration, and clusters. | Foundation to intermediate; use the version and environment expected by the tutorial. |
| [HashiCorp tutorials](https://developer.hashicorp.com/tutorials) | Find product-maintained tutorials for infrastructure, images, secrets, and related workflows. | Foundation to advanced; tutorial dependencies and cloud charges vary. |
| [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) | Practice SQL and database concepts with the project's introductory material. | Foundation; public tutorial. Work in a disposable database, inspect statement effects, and remove practice data afterward. |
| [DORA Guides](https://dora.dev/guides/) | Explore delivery measurement, value-stream analysis, and improvement guidance. | Intermediate; use measures to investigate system behavior rather than rank individuals. |
| [DORA capabilities](https://dora.dev/capabilities/) | Find research-informed delivery and organizational capability references. | Intermediate; assess evidence and local constraints before prioritizing changes. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |

## Foundation-level SRE training

Use this direct beginner module to understand the operating practice and human responsibilities before turning to advanced implementation references. It is a topic option, not a required curriculum.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Microsoft Learn: introduction to SRE](https://learn.microsoft.com/en-us/training/modules/intro-to-site-reliability-engineering/) | Browse a beginner module explaining SRE context, principles, human responsibilities, and getting started. | Foundation; publicly readable training module with no stated prerequisites. Sign-in is required for profile-linked assessment results; it is introductory guidance, not a production implementation lab. |

[Browse the other collections](README.md#resource-collections)

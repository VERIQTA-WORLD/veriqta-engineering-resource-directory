# Reliability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Reliability methods and evidence](#reliability-methods-and-evidence)
- [Distributed systems and failure testing](#distributed-systems-and-failure-testing)
- [Practical measurement and improvement](#practical-measurement-and-improvement)
- [Foundation-level SRE training](#foundation-level-sre-training)

## Reliability methods and evidence

Use the books and focused chapters to connect service objectives, monitoring, testing, and incident learning. Book availability and reading scope differ by publisher.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Google SRE books](https://sre.google/books/) | Locate original reliability, operational, and secure-system engineering references. | Intermediate to advanced; examples reflect their authors' environments and publication periods. |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html) | Explore security and reliability together in system design and operations. | Advanced; openly readable. Examples require interpretation for your environment. |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |

## Distributed systems and failure testing

Read the documented claims and tested conditions. A failure analysis for one version or configuration is not proof about every deployment.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Find the author's book information and supporting resources for data-system design. | Intermediate to advanced; public book website. Full books are separate purchases; choose an edition and check publication details. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Jepsen analyses](https://jepsen.io/analyses) | Read independent system-consistency investigations and their tested assumptions. | Advanced; public research collection. Findings are tied to tested versions and scenarios; do not transfer a historical verdict to every later release. |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |
| [Chaos Toolkit documentation](https://chaostoolkit.org/) | Explore experiment definitions, drivers, and execution guidance for hypothesis-based failure testing. | Advanced; public project documentation. Extensions need separate review; experiments can affect availability and data. |

## Practical measurement and improvement

Use diagnostic, performance, and delivery references to decide what to measure and which improvements deserve priority.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [The USE method](https://www.brendangregg.com/usemethod.html) | Organize resource analysis around utilization, saturation, and errors. | Intermediate; public author reference. High utilization alone does not establish the limiting resource. |
| [Brendan Gregg: systems performance](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) | Find the author's description and supporting material for a systems-performance reference. | Intermediate to advanced; public book page. The book itself is a separate purchase; review edition-specific tools. |
| [DORA Guides](https://dora.dev/guides/) | Explore delivery measurement, value-stream analysis, and improvement guidance. | Intermediate; use measures to investigate system behavior rather than rank individuals. |
| [DORA capabilities](https://dora.dev/capabilities/) | Find research-informed delivery and organizational capability references. | Intermediate; assess evidence and local constraints before prioritizing changes. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize cost accountability, allocation, forecasting, and optimization work. | Intermediate; a practice framework, not a tool or a guarantee of savings. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |

## Foundation-level SRE training

Use this direct beginner module to understand the operating practice and human responsibilities before turning to advanced implementation references. It is a topic option, not a required curriculum.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Microsoft Learn: introduction to SRE](https://learn.microsoft.com/en-us/training/modules/intro-to-site-reliability-engineering/) | Browse a beginner module explaining SRE context, principles, human responsibilities, and getting started. | Foundation; publicly readable training module with no stated prerequisites. Sign-in is required for profile-linked assessment results; it is introductory guidance, not a production implementation lab. |

[Browse the other collections](README.md#resource-collections)

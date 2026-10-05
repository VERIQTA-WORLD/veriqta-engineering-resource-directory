# Site reliability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Core SRE material](#core-sre-material)
- [Load, data, and distributed behavior](#load-data-and-distributed-behavior)
- [Implementation and improvement collections](#implementation-and-improvement-collections)
- [Foundation-level SRE training](#foundation-level-sre-training)

## Core SRE material

These free books and focused chapters cover the operating model, service objectives, signals, on-call, incidents, testing, and toil. Browse by the problem you are solving.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Google SRE books](https://sre.google/books/) | Locate original reliability, operational, and secure-system engineering references. | Intermediate to advanced; examples reflect their authors' environments and publication periods. |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html) | Explore security and reliability together in system design and operations. | Advanced; openly readable. Examples require interpretation for your environment. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Being on-call](https://sre.google/sre-book/being-on-call/) | Review escalation, operating preparedness, and the human responsibilities of incident coverage. | Foundation onward; public chapter. Staffing and escalation arrangements must be agreed locally. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [The evolution of automation](https://sre.google/sre-book/automation-at-google/) | Study how automation changes operating practices and control boundaries. | Intermediate; public book chapter. Large-scale examples are design references, not a requirement to build an equivalent platform. |

## Load, data, and distributed behavior

Use performance and data references to understand conditions that ordinary dashboards may not explain. Publisher pages for commercial books describe scope and access rather than provide the whole text.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [The USE method](https://www.brendangregg.com/usemethod.html) | Organize resource analysis around utilization, saturation, and errors. | Intermediate; public author reference. High utilization alone does not establish the limiting resource. |
| [Brendan Gregg: systems performance](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) | Find the author's description and supporting material for a systems-performance reference. | Intermediate to advanced; public book page. The book itself is a separate purchase; review edition-specific tools. |
| [Non-abstract large system design](https://sre.google/workbook/non-abstract-design/) | Connect system design to concrete capacity, dependency, and failure assumptions. | Advanced; public workbook chapter. Recalculate workload assumptions rather than reusing example capacity figures. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Google SRE Workbook: managing load](https://sre.google/workbook/managing-load/) | Connect load balancing, overload management, and failure handling to service behavior. | Intermediate; public chapter. Adapt the examples to local traffic, dependencies, and recovery constraints. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Data processing pipelines](https://sre.google/workbook/data-processing/) | Study reliability concerns in scheduled and streaming processing, including timeliness and completion. | Intermediate to advanced; public chapter. User-facing correctness and freshness may matter more than process uptime. |
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Find the author's book information and supporting resources for data-system design. | Intermediate to advanced; public book website. Full books are separate purchases; choose an edition and check publication details. |
| [CMU database systems course site](https://15445.courses.cs.cmu.edu/) | Find university database-system lectures, readings, and project guidance. | Advanced; public course discovery site. Semester content changes; programming and database foundations are prerequisites. |

## Implementation and improvement collections

Choose implementation tutorials and talks with a clear connection to the service. Delivery research and economic frameworks support improvement decisions but do not prescribe a universal target.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes tutorials](https://kubernetes.io/docs/tutorials/) | Study official walkthroughs for workloads, services, configuration, and clusters. | Foundation to intermediate; use the version and environment expected by the tutorial. |
| [HashiCorp tutorials](https://developer.hashicorp.com/tutorials) | Find product-maintained tutorials for infrastructure, images, secrets, and related workflows. | Foundation to advanced; tutorial dependencies and cloud charges vary. |
| [Pulumi tutorials](https://www.pulumi.com/tutorials/) | Find infrastructure learning examples organized around supported tools and platforms. | Intermediate; review account, language, and cloud requirements before starting. |
| [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) | Practice SQL and database concepts with the project's introductory material. | Foundation; public tutorial. Work in a disposable database, inspect statement effects, and remove practice data afterward. |
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

# Scalability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Performance and bottleneck reasoning](#performance-and-bottleneck-reasoning)
- [Distributed data and service growth](#distributed-data-and-service-growth)
- [Hands-on implementation and economics](#hands-on-implementation-and-economics)

## Performance and bottleneck reasoning

Use measurement methods and focused performance references to interpret test results. Tool output requires workload and environment context.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [The USE method](https://www.brendangregg.com/usemethod.html) | Organize resource analysis around utilization, saturation, and errors. | Intermediate; public author reference. High utilization alone does not establish the limiting resource. |
| [Brendan Gregg: systems performance](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) | Find the author's description and supporting material for a systems-performance reference. | Intermediate to advanced; public book page. The book itself is a separate purchase; review edition-specific tools. |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |
| [Non-abstract large system design](https://sre.google/workbook/non-abstract-design/) | Connect system design to concrete capacity, dependency, and failure assumptions. | Advanced; public workbook chapter. Recalculate workload assumptions rather than reusing example capacity figures. |

## Distributed data and service growth

Read state, consensus, pipelines, and overload material alongside implementation documentation. A distributed design must still satisfy the service's correctness requirements.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Find the author's book information and supporting resources for data-system design. | Intermediate to advanced; public book website. Full books are separate purchases; choose an edition and check publication details. |
| [CMU database systems course site](https://15445.courses.cs.cmu.edu/) | Find university database-system lectures, readings, and project guidance. | Advanced; public course discovery site. Semester content changes; programming and database foundations are prerequisites. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Data processing pipelines](https://sre.google/workbook/data-processing/) | Study reliability concerns in scheduled and streaming processing, including timeliness and completion. | Intermediate to advanced; public chapter. User-facing correctness and freshness may matter more than process uptime. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |

## Hands-on implementation and economics

Use upstream tutorials and selected community material to explore implementations. Costs depend on the chosen environment and workload.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes tutorials](https://kubernetes.io/docs/tutorials/) | Study official walkthroughs for workloads, services, configuration, and clusters. | Foundation to intermediate; use the version and environment expected by the tutorial. |
| [HashiCorp tutorials](https://developer.hashicorp.com/tutorials) | Find product-maintained tutorials for infrastructure, images, secrets, and related workflows. | Foundation to advanced; tutorial dependencies and cloud charges vary. |
| [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) | Practice SQL and database concepts with the project's introductory material. | Foundation; public tutorial. Work in a disposable database, inspect statement effects, and remove practice data afterward. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize cost accountability, allocation, forecasting, and optimization work. | Intermediate; a practice framework, not a tool or a guarantee of savings. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |

[Browse the other collections](README.md#resource-collections)

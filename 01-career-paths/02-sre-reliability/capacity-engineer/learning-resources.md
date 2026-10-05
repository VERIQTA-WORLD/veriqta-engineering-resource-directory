# Capacity engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Measurement and system behavior](#measurement-and-system-behavior)
- [Load, overload, and service reliability](#load-overload-and-service-reliability)
- [Data and economics](#data-and-economics)

## Measurement and system behavior

These references explain how to reason from resource evidence rather than treat high utilization as the entire diagnosis.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [The USE method](https://www.brendangregg.com/usemethod.html) | Organize resource analysis around utilization, saturation, and errors. | Intermediate; public author reference. High utilization alone does not establish the limiting resource. |
| [Brendan Gregg: systems performance](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) | Find the author's description and supporting material for a systems-performance reference. | Intermediate to advanced; public book page. The book itself is a separate purchase; review edition-specific tools. |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Non-abstract large system design](https://sre.google/workbook/non-abstract-design/) | Connect system design to concrete capacity, dependency, and failure assumptions. | Advanced; public workbook chapter. Recalculate workload assumptions rather than reusing example capacity figures. |

## Load, overload, and service reliability

Read the mechanisms and limitations behind workload control and failure capacity. Google's examples are references rather than mandatory scale targets.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Google SRE Workbook: managing load](https://sre.google/workbook/managing-load/) | Connect load balancing, overload management, and failure handling to service behavior. | Intermediate; public chapter. Adapt the examples to local traffic, dependencies, and recovery constraints. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [SLO engineering case studies](https://sre.google/workbook/slo-engineering-case-studies/) | Compare service-objective decisions and measurement approaches in concrete cases. | Intermediate; public chapter. Keep the service boundary and user expectations explicit. |

## Data and economics

Use these to connect queueing and data dependencies to practical database behavior and expenditure.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Find the author's book information and supporting resources for data-system design. | Intermediate to advanced; public book website. Full books are separate purchases; choose an edition and check publication details. |
| [PostgreSQL EXPLAIN guidance](https://www.postgresql.org/docs/current/using-explain.html) | Read execution plans and investigate query behavior with documented planner concepts. | Intermediate; public guide. EXPLAIN ANALYZE executes the query; use controlled targets for statements with side effects. |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize cost accountability, allocation, forecasting, and optimization work. | Intermediate; a practice framework, not a tool or a guarantee of savings. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |

[Browse the other collections](README.md#resource-collections)

# Chaos engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Experiment principles and operational method](#experiment-principles-and-operational-method)
- [Failure mechanisms and integrity](#failure-mechanisms-and-integrity)
- [Original incidents and community material](#original-incidents-and-community-material)

## Experiment principles and operational method

Use hypothesis-driven testing and reliability references to make experiments answer a specific engineering question.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |

## Failure mechanisms and integrity

Understand how retry storms, overload, consensus loss, or incorrect recovery can turn a local disturbance into a broader incident.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Google SRE Workbook: managing load](https://sre.google/workbook/managing-load/) | Connect load balancing, overload management, and failure handling to service behavior. | Intermediate; public chapter. Adapt the examples to local traffic, dependencies, and recovery constraints. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |

## Original incidents and community material

Use documented historical failures to generate candidate hypotheses. Do not infer causes that the original report does not establish.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Cloudflare outage of July 2, 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/) | Read the original account of a globally propagated service failure and its operating lessons. | Intermediate; public historical incident report. Retain the documented cause and timeline; it does not describe every later system version. |
| [Cloudflare control-plane and analytics outage](https://blog.cloudflare.com/post-mortem-on-cloudflare-control-plane-and-analytics-outage/) | Compare dependency, datacenter, and recovery concerns in an original outage account. | Advanced; public historical postmortem. Distinguish affected control-plane and analytics functions from unaffected services. |
| [GitHub October 2018 incident analysis](https://github.blog/news-insights/company-news/oct21-post-incident-analysis/) | Read the original incident analysis of database topology and recovery decisions. | Advanced; public historical report. Findings describe that incident and architecture, not a current service guarantee. |
| [GitLab database incident postmortem](https://about.gitlab.com/blog/gitlab-dot-com-database-incident/) | Study operational mistakes, recovery dependencies, and backup-validation lessons in an original report. | Intermediate; public historical incident account. Do not confuse configured backup procedures with demonstrated restore capability. |
| [AWS S3 service disruption summary, 2017](https://aws.amazon.com/message/41926/) | Read the provider's original account of a historical regional service disruption. | Intermediate; public historical report. Its documented scope and corrective actions are specific to that event. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |

[Browse the other collections](README.md#resource-collections)

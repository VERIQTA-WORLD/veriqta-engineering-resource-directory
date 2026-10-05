# Reliability engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Maintain a reliability model for important outcomes](#maintain-a-reliability-model-for-important-outcomes)
- [Investigate failures with reproducible evidence](#investigate-failures-with-reproducible-evidence)
- [Validate controls, changes, and recovery](#validate-controls-changes-and-recovery)
- [Prioritize and follow through on improvements](#prioritize-and-follow-through-on-improvements)
- [Maintain response coordination and escalation](#maintain-response-coordination-and-escalation)

## Maintain a reliability model for important outcomes

Record success criteria, data sources, dependency assumptions, ownership, and risk. Review objectives with the people who use and operate the service.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [SLO engineering case studies](https://sre.google/workbook/slo-engineering-case-studies/) | Compare service-objective decisions and measurement approaches in concrete cases. | Intermediate; public chapter. Keep the service boundary and user expectations explicit. |
| [Example SLO document](https://sre.google/workbook/slo-document/) | Review a worked document connecting service indicators, targets, and measurement details. | Foundation onward; public appendix. Adapt the scope and data sources instead of copying its numbers. |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |

## Investigate failures with reproducible evidence

Use signal definitions and diagnostic context to distinguish symptoms, contributing conditions, and verified causes. Preserve useful incident evidence with appropriate access.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [Wireshark user guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Review capture setup, protocol analysis, display filtering, and packet inspection workflows. | Foundation to advanced; public manual currently displaying development version 4.7.4. Match the installed release; packet capture requires permission and careful handling of sensitive data. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |

## Validate controls, changes, and recovery

Check whether isolation, release controls, retries, recovery, and data safeguards deliver the intended outcome under the defined test conditions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. |

## Prioritize and follow through on improvements

Connect repeated failure patterns and toil to an owner, a proposed change, and a verification result. Review capacity and cost consequences alongside reliability.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Example error budget policy](https://sre.google/workbook/error-budget-policy/) | Find a concrete example of how reliability evidence can influence change decisions. | Intermediate; public appendix. A policy needs agreed authority, exceptions, and a measured service boundary. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [The evolution of automation](https://sre.google/sre-book/automation-at-google/) | Study how automation changes operating practices and control boundaries. | Intermediate; public book chapter. Large-scale examples are design references, not a requirement to build an equivalent platform. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [DORA capabilities](https://dora.dev/capabilities/) | Find research-informed delivery and organizational capability references. | Intermediate; assess evidence and local constraints before prioritizing changes. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Intermediate; cost work requires billing and usage data, not estimates alone. |
| [Cloudflare outage of July 2, 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/) | Read the original account of a globally propagated service failure and its operating lessons. | Intermediate; public historical incident report. Retain the documented cause and timeline; it does not describe every later system version. |
| [GitLab database incident postmortem](https://about.gitlab.com/blog/gitlab-dot-com-database-incident/) | Study operational mistakes, recovery dependencies, and backup-validation lessons in an original report. | Intermediate; public historical incident account. Do not confuse configured backup procedures with demonstrated restore capability. |

## Maintain response coordination and escalation

Review alert delivery, ownership changes, handoffs, and response roles. Test the chosen coordination path and preserve an alternative when an integration or communication service is unavailable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PagerDuty incident documentation](https://support.pagerduty.com/main/docs/incidents) | Inspect incident states, ownership, response, and notification behavior in a hosted incident platform. | Intermediate; public vendor documentation. Using the platform requires an account and suitable service access; review schedules, integrations, escalation, and feature availability. |
| [incident.io help center](https://docs.incident.io/) | Compare a hosted platform's incident response, on-call, alerting, and workflow documentation. | Intermediate; public vendor help center. Platform use requires an account and appropriate access; select direct guides and check integration and product boundaries. |
| [Being on-call](https://sre.google/sre-book/being-on-call/) | Review escalation, operating preparedness, and the human responsibilities of incident coverage. | Foundation onward; public chapter. Staffing and escalation arrangements must be agreed locally. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |

[Browse the other collections](README.md#resource-collections)

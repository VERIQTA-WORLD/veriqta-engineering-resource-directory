# Chaos engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Approve and constrain the experiment](#approve-and-constrain-the-experiment)
- [Observe service outcomes and fault containment](#observe-service-outcomes-and-fault-containment)
- [Protect state and prove cleanup](#protect-state-and-prove-cleanup)
- [Turn results into reliability improvements](#turn-results-into-reliability-improvements)

## Approve and constrain the experiment

Agree authority, target identifiers, steady-state thresholds, duration, abort conditions, communication, and recovery responsibilities before execution.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |
| [AWS Fault Injection Service documentation](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html) | Review managed fault experiments, targets, actions, and operating controls. | Advanced; public documentation. AWS account permissions and charges apply; review stop conditions and each action's recovery behavior. |
| [Azure Chaos Studio Workspaces documentation (preview)](https://learn.microsoft.com/en-us/azure/chaos-studio/) | Evaluate Azure fault experiments and service-specific target requirements. | Intermediate to advanced; public documentation for a preview service. Check feature scope, supported targets, account requirements, and preview limitations before planning an experiment. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Intermediate; assess escalation paths, broad grants, and service-account use. |

## Observe service outcomes and fault containment

Preserve measurements that distinguish the injected fault, dependency effects, useful throughput, and recovery. Test abort and diagnostic paths too.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Prometheus alerting rules](https://prometheus.io/docs/prometheus/latest/configuration/alerting_rules/) | Define actionable alert conditions and understand their evaluation behavior. | Intermediate; public reference. Alert expressions need routing, ownership, and diagnostic context. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |

## Protect state and prove cleanup

Treat removed experiment objects and restored data as different checks. Confirm no residual fault, changed route, stressed process, or damaged test data remains.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Velero documentation](https://velero.io/docs/) | Review Kubernetes backup and restore mechanisms and provider requirements. | Advanced; rehearse restore and verify application data consistency, not only object recreation. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. |
| [Toxiproxy usage and API examples](https://github.com/Shopify/toxiproxy/blob/main/README.md) | Inspect proxy configuration and fault-control examples before writing a dependency-failure test. | Intermediate; public project examples. Reset faults and remove the disposable proxy; never intercept unrelated traffic. |

## Turn results into reliability improvements

Record what happened, what the hypothesis missed, and which change will be tested next. Keep incident response ready during any consequential experiment.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |
| [Cloudflare control-plane and analytics outage](https://blog.cloudflare.com/post-mortem-on-cloudflare-control-plane-and-analytics-outage/) | Compare dependency, datacenter, and recovery concerns in an original outage account. | Advanced; public historical postmortem. Distinguish affected control-plane and analytics functions from unaffected services. |
| [GitLab database incident postmortem](https://about.gitlab.com/blog/gitlab-dot-com-database-incident/) | Study operational mistakes, recovery dependencies, and backup-validation lessons in an original report. | Intermediate; public historical incident account. Do not confuse configured backup procedures with demonstrated restore capability. |
| [Example error budget policy](https://sre.google/workbook/error-budget-policy/) | Find a concrete example of how reliability evidence can influence change decisions. | Intermediate; public appendix. A policy needs agreed authority, exceptions, and a measured service boundary. |

[Browse the other collections](README.md#resource-collections)

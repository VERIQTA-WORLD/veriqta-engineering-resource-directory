# Resilience engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [Dependencies, retries, and idempotency](#dependencies-retries-and-idempotency)
- [State protection and recovery](#state-protection-and-recovery)
- [Platform and provider disruption](#platform-and-provider-disruption)
- [Fault-injection and recovery evidence](#fault-injection-and-recovery-evidence)

## Dependencies, retries, and idempotency

Review timeout, retry, circuit, and duplicate-request semantics together. Retried work must be safe and must not overwhelm the dependency being recovered.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [Azure retry pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/retry) | Review transient-fault handling and retry design trade-offs. | Intermediate; public architecture pattern. Retrying permanent failures or non-idempotent operations can worsen the incident. |
| [Azure circuit breaker pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker) | Compare dependency-failure containment and recovery-probe behavior. | Intermediate; public pattern. Thresholds and reset behavior must match the dependency and user impact. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |

## State protection and recovery

Select documentation for the deployed database and storage arrangement. Measure restore outcomes and assess data loss rather than infer recovery from replication status alone.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Advanced; use documentation matching the deployed database version and test restored data. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. |
| [Patroni documentation](https://patroni.readthedocs.io/en/latest/) | Compare PostgreSQL high-availability orchestration and its distributed coordination dependencies. | Advanced; public project reference. Review fencing, datastore behavior, failover policy, and recovery; an orchestrator is not a backup. |
| [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/) | Compare persistence modes and their durability and restart implications. | Intermediate; public guide. Persisted data and replicas are not proof of tested recovery or acceptable data loss. |
| [Redis Sentinel](https://redis.io/docs/latest/operate/oss_and_stack/management/sentinel/) | Review Redis monitoring and failover coordination in the documented Sentinel model. | Advanced; public reference. Clients, quorum arrangements, and network partitions affect failover outcomes. |
| [MySQL replication reference](https://dev.mysql.com/doc/refman/8.4/en/replication.html) | Review replication arrangements and failure-sensitive operating behavior. | Advanced; public manual. Replication consistency and recovery depend on the chosen configuration and topology. |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |

## Platform and provider disruption

Understand disruption, resource, control-plane, and provider health behavior before choosing a failure scenario.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Intermediate; a disruption budget is not a universal guarantee against outages. |
| [Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) | Review health-check semantics and configuration. | Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/) | Compare production setup considerations and operating models. | Advanced; managed services retain workload and configuration responsibilities. |
| [AWS Health documentation](https://docs.aws.amazon.com/health/) | Find provider-event visibility and account-specific health information guidance. | Intermediate; public documentation. Provider status is one signal; it does not replace your own service measurements. |
| [Azure Service Health documentation](https://learn.microsoft.com/en-us/azure/service-health/) | Review provider incident, maintenance, and advisory visibility for Azure workloads. | Foundation onward; public reference. Access to account-specific information requires appropriate subscription permissions. |
| [Google Cloud Service Health documentation](https://cloud.google.com/service-health/docs/overview) | Find provider health and incident visibility guidance for cloud operations. | Intermediate; public reference. Compare provider events with workload telemetry and dependency evidence. |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |

## Fault-injection and recovery evidence

Read supported actions, constraints, cleanup behavior, and instrumentation requirements for the chosen experiment.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Chaos Mesh documentation](https://chaos-mesh.org/docs/) | Find experiment types, scheduling, permissions, and fault-injection guidance. | Advanced; public project documentation. Cluster and node effects vary by experiment; define abort conditions and verify recovery. |
| [LitmusChaos documentation](https://docs.litmuschaos.io/) | Review experiment and workflow guidance for resilience testing. | Advanced; public documentation. Inspect experiment privileges, target selection, cleanup, and recovery checks. |
| [AWS Fault Injection Service documentation](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html) | Review managed fault experiments, targets, actions, and operating controls. | Advanced; public documentation. AWS account permissions and charges apply; review stop conditions and each action's recovery behavior. |
| [Azure Chaos Studio Workspaces documentation (preview)](https://learn.microsoft.com/en-us/azure/chaos-studio/) | Evaluate Azure fault experiments and service-specific target requirements. | Intermediate to advanced; public documentation for a preview service. Check feature scope, supported targets, account requirements, and preview limitations before planning an experiment. |
| [Toxiproxy usage and API examples](https://github.com/Shopify/toxiproxy/blob/main/README.md) | Inspect proxy configuration and fault-control examples before writing a dependency-failure test. | Intermediate; public project examples. Reset faults and remove the disposable proxy; never intercept unrelated traffic. |
| [Testing for reliability](https://sre.google/sre-book/testing-reliability/) | Compare test types and their relationship to failure detection and operational confidence. | Intermediate; public chapter. A passing test covers its scenarios, not every failure mode. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |

[Browse the other collections](README.md#resource-collections)

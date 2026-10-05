# Chaos engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [Experiment actions and controls](#experiment-actions-and-controls)
- [Workload health and maintenance](#workload-health-and-maintenance)
- [Measurements and state protection](#measurements-and-state-protection)

## Experiment actions and controls

Inspect the chosen action, privileges, target selectors, duration, stop mechanisms, and cleanup behavior. Provider and Kubernetes actions have different constraints.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Chaos Mesh documentation](https://chaos-mesh.org/docs/) | Find experiment types, scheduling, permissions, and fault-injection guidance. | Advanced; public project documentation. Cluster and node effects vary by experiment; define abort conditions and verify recovery. |
| [LitmusChaos documentation](https://docs.litmuschaos.io/) | Review experiment and workflow guidance for resilience testing. | Advanced; public documentation. Inspect experiment privileges, target selection, cleanup, and recovery checks. |
| [Chaos Toolkit documentation](https://chaostoolkit.org/) | Explore experiment definitions, drivers, and execution guidance for hypothesis-based failure testing. | Advanced; public project documentation. Extensions need separate review; experiments can affect availability and data. |
| [AWS Fault Injection Service documentation](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html) | Review managed fault experiments, targets, actions, and operating controls. | Advanced; public documentation. AWS account permissions and charges apply; review stop conditions and each action's recovery behavior. |
| [Azure Chaos Studio Workspaces documentation (preview)](https://learn.microsoft.com/en-us/azure/chaos-studio/) | Evaluate Azure fault experiments and service-specific target requirements. | Intermediate to advanced; public documentation for a preview service. Check feature scope, supported targets, account requirements, and preview limitations before planning an experiment. |
| [AWS FIS tutorial: instance stop and start](https://docs.aws.amazon.com/fis/latest/userguide/fis-tutorial-stop-instances.html) | Create an experiment that stops and restarts two test EC2 instances, then verify the observed instance transitions. | Intermediate; public cloud tutorial. Requires test instances, experiment permissions, and an account; compute and service use can incur charges. |
| [Toxiproxy usage and API examples](https://github.com/Shopify/toxiproxy/blob/main/README.md) | Inspect proxy configuration and fault-control examples before writing a dependency-failure test. | Intermediate; public project examples. Reset faults and remove the disposable proxy; never intercept unrelated traffic. |
| [stress-ng](https://github.com/ColinIanKing/stress-ng) | Explore controlled resource stressors for testing host and workload behavior. | Advanced; public project repository. Stressors can destabilize a host; use disposable environments and stop all stress processes afterward. |

## Workload health and maintenance

Read workload and scheduling behavior before testing disruption. A synthetic fault should not conceal unsupported maintenance or readiness settings.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) | Review health-check semantics and configuration. | Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Intermediate; a disruption budget is not a universal guarantee against outages. |
| [Kubernetes node drain](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/) | Understand workload eviction during node maintenance. | Intermediate; public task guide. Draining changes availability; disruption budgets, local data, and unmanaged pods affect behavior. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Intermediate; assess escalation paths, broad grants, and service-account use. |

## Measurements and state protection

Validate the signals and the recovery path before risking data. Preserve separate evidence for availability, integrity, and restored data.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Prometheus alerting rules](https://prometheus.io/docs/prometheus/latest/configuration/alerting_rules/) | Define actionable alert conditions and understand their evaluation behavior. | Intermediate; public reference. Alert expressions need routing, ownership, and diagnostic context. |
| [Prometheus rule unit tests](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/) | Test rule behavior against synthetic time-series inputs before changing production alerts. | Intermediate; public practical reference. Synthetic series do not establish live scrape or routing correctness. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |

[Browse the other collections](README.md#resource-collections)

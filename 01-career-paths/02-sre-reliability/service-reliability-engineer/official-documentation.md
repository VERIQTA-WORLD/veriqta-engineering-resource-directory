# Service reliability engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [Service objectives and instrumentation](#service-objectives-and-instrumentation)
- [Dependencies and service behavior](#dependencies-and-service-behavior)
- [Change and production diagnosis](#change-and-production-diagnosis)
- [Recovery and provider dependencies](#recovery-and-provider-dependencies)
- [Provider workload signals](#provider-workload-signals)

## Service objectives and instrumentation

Define successful outcomes, measurement windows, aggregation, and alert response. Use probes for their documented semantics rather than a universal health verdict.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [SLO engineering case studies](https://sre.google/workbook/slo-engineering-case-studies/) | Compare service-objective decisions and measurement approaches in concrete cases. | Intermediate; public chapter. Keep the service boundary and user expectations explicit. |
| [Example SLO document](https://sre.google/workbook/slo-document/) | Review a worked document connecting service indicators, targets, and measurement details. | Foundation onward; public appendix. Adapt the scope and data sources instead of copying its numbers. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Prometheus instrumentation practices](https://prometheus.io/docs/practices/instrumentation/) | Select metrics and labels that answer operating questions without uncontrolled cardinality. | Intermediate; public guide. Instrumentation overhead and confidential label values need review. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) | Review health-check semantics and configuration. | Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies. |

## Dependencies and service behavior

Consult retry, idempotency, traffic, resource, and state guidance for the implementation in use. Verify the behavior of timeouts and partial failures.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [Azure retry pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/retry) | Review transient-fault handling and retry design trade-offs. | Intermediate; public architecture pattern. Retrying permanent failures or non-idempotent operations can worsen the incident. |
| [Azure circuit breaker pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker) | Compare dependency-failure containment and recovery-probe behavior. | Intermediate; public pattern. Thresholds and reset behavior must match the dependency and user impact. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/) | Compare persistence modes and their durability and restart implications. | Intermediate; public guide. Persisted data and replicas are not proof of tested recovery or acceptable data loss. |

## Change and production diagnosis

Review rollout, configuration, credentials, and runtime debugging before a release or incident. Keep evidence tied to the affected version and environment.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |
| [Release engineering](https://sre.google/sre-book/release-engineering/) | Study an original account of build, release, and deployment engineering. | Intermediate to advanced; Google-specific practices require adaptation. |
| [Configuration design and best practices](https://sre.google/workbook/configuration-design/) | Review interfaces, validation, and change control for configuration-driven systems. | Intermediate; public chapter. Syntax validation alone cannot establish a safe operational change. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review workflow, dependency, runner, and credential security considerations. | Intermediate; apply the guidance to the repository trust model and runner arrangement. |
| [GitHub Actions OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect) | Evaluate identity federation between workflows and external providers. | Advanced; public conceptual guide. Trust policy must bind the intended repository and execution context, not merely the identity provider. |
| [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) | Locate workload debugging references for deployment and runtime failures. | Intermediate; establish scope before applying changes. Read permissions and command effects. |
| [PostgreSQL explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html) | Understand lock conflicts and deadlock behavior before intervening in blocked database work. | Intermediate; public reference. Terminating a session can abort transactions and affect application behavior. |
| [PostgreSQL EXPLAIN guidance](https://www.postgresql.org/docs/current/using-explain.html) | Read execution plans and investigate query behavior with documented planner concepts. | Intermediate; public guide. EXPLAIN ANALYZE executes the query; use controlled targets for statements with side effects. |
| [Wireshark user guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Review capture setup, protocol analysis, display filtering, and packet inspection workflows. | Foundation to advanced; public manual currently displaying development version 4.7.4. Match the installed release; packet capture requires permission and careful handling of sensitive data. |

## Recovery and provider dependencies

Use service-specific restore guidance and provider-health information as supporting evidence. Provider status does not replace observation of the service.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Advanced; use documentation matching the deployed database version and test restored data. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |
| [AWS Health documentation](https://docs.aws.amazon.com/health/) | Find provider-event visibility and account-specific health information guidance. | Intermediate; public documentation. Provider status is one signal; it does not replace your own service measurements. |
| [Azure Service Health documentation](https://learn.microsoft.com/en-us/azure/service-health/) | Review provider incident, maintenance, and advisory visibility for Azure workloads. | Foundation onward; public reference. Access to account-specific information requires appropriate subscription permissions. |
| [Google Cloud Service Health documentation](https://cloud.google.com/service-health/docs/overview) | Find provider health and incident visibility guidance for cloud operations. | Intermediate; public reference. Compare provider events with workload telemetry and dependency evidence. |

## Provider workload signals

Use these documentation entry points to find the selected provider's metrics, logs, alerting, identity, and retention guidance. Check actual service impact independently of provider status.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon CloudWatch documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) | Find AWS monitoring, alarms, logs, service signals, and collection references for workload investigation. | Intermediate; public provider documentation. An AWS account and relevant permissions are needed to operate the service; collection, retention, and features have separate billing conditions. |
| [Azure Monitor overview](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview) | Review Azure's monitoring components and links for application and infrastructure observation. | Intermediate; public provider overview. Check the selected component's data collection, identity, retention, and charging model before deployment. |
| [Google Cloud Monitoring overview](https://cloud.google.com/monitoring/docs/monitoring-overview) | Find Google Cloud metric collection, dashboards, alerting, and monitoring integration references. | Intermediate; public provider documentation. Operating access requires appropriate project permissions; telemetry volume and selected services affect charges. |

[Browse the other collections](README.md#resource-collections)

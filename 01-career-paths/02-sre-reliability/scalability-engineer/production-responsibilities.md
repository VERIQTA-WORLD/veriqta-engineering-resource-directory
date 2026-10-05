# Scalability engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Maintain a useful growth and workload model](#maintain-a-useful-growth-and-workload-model)
- [Investigate saturation and uneven distribution](#investigate-saturation-and-uneven-distribution)
- [Validate elasticity and overload containment](#validate-elasticity-and-overload-containment)
- [Review data growth, telemetry, and economics](#review-data-growth-telemetry-and-economics)

## Maintain a useful growth and workload model

Track request mix, data volume, placement, peak load, limits, and uncertainty. Keep test conditions comparable and report the effect on user outcomes.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Non-abstract large system design](https://sre.google/workbook/non-abstract-design/) | Connect system design to concrete capacity, dependency, and failure assumptions. | Advanced; public workbook chapter. Recalculate workload assumptions rather than reusing example capacity figures. |
| [k6 arrival-rate executors](https://grafana.com/docs/k6/latest/using-k6/scenarios/concepts/arrival-rate-vu-allocation/) | Understand workload generation and virtual-user allocation for arrival-rate tests. | Intermediate; public reference. Generator capacity and dropped iterations can distort the apparent system limit. |
| [k6 thresholds](https://grafana.com/docs/k6/latest/using-k6/thresholds/) | Define explicit load-test acceptance conditions rather than relying on a completed run. | Intermediate; public reference. Thresholds need a justified target, representative workload, and sufficient observations. |
| [The USE method](https://www.brendangregg.com/usemethod.html) | Organize resource analysis around utilization, saturation, and errors. | Intermediate; public author reference. High utilization alone does not establish the limiting resource. |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |

## Investigate saturation and uneven distribution

Locate the constrained resource or partition before scaling. Correlate proxy, database, host, and application evidence.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Load balancing at the frontend](https://sre.google/sre-book/load-balancing-frontend/) | Explore traffic distribution and frontend reliability across infrastructure boundaries. | Advanced; public chapter. Provider and network topology determine which mechanisms are available. |
| [Load balancing in the datacenter](https://sre.google/sre-book/load-balancing-datacenter/) | Compare service load-balancing behavior, health signals, and backend selection. | Advanced; public chapter. A healthy endpoint may still be unable to satisfy the requested operation. |
| [PostgreSQL EXPLAIN guidance](https://www.postgresql.org/docs/current/using-explain.html) | Read execution plans and investigate query behavior with documented planner concepts. | Intermediate; public guide. EXPLAIN ANALYZE executes the query; use controlled targets for statements with side effects. |
| [PostgreSQL explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html) | Understand lock conflicts and deadlock behavior before intervening in blocked database work. | Intermediate; public reference. Terminating a session can abort transactions and affect application behavior. |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [MySQL Performance Schema](https://dev.mysql.com/doc/refman/8.4/en/performance-schema.html) | Investigate instrumented database execution and resource use through the supported diagnostic system. | Advanced; public version-specific reference. Instrumentation, privileges, and overhead need review. |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |

## Validate elasticity and overload containment

Check time to useful capacity, quotas, dependency limits, and failure headroom. Test overload behavior when expansion is unavailable or too slow.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |
| [Kubernetes Cluster Autoscaler](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler) | Review node-capacity scaling and provider integration constraints. | Advanced; public project repository. Provider quotas, node-group limits, and workload scheduling constraints affect expansion. |
| [Karpenter documentation](https://karpenter.sh/docs/) | Compare node provisioning and disruption behavior for supported Kubernetes environments. | Advanced; public project documentation. Provider compatibility, IAM permissions, quotas, and replacement effects require review. |
| [KEDA documentation](https://keda.sh/docs/) | Evaluate event-driven workload autoscaling and its external metric dependencies. | Intermediate; public versioned project documentation. Scaling cannot repair slow dependencies or supply unavailable infrastructure capacity. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Google SRE Workbook: managing load](https://sre.google/workbook/managing-load/) | Connect load balancing, overload management, and failure handling to service behavior. | Intermediate; public chapter. Adapt the examples to local traffic, dependencies, and recovery constraints. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |

## Review data growth, telemetry, and economics

Include maintenance, recovery, cardinality, storage retention, and cost allocation in scaling decisions. Review regressions and record verified changes.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL routine vacuuming](https://www.postgresql.org/docs/current/routine-vacuuming.html) | Investigate maintenance, dead tuples, statistics, and transaction-ID safety concerns. | Intermediate; public guide. Maintenance changes can affect I/O and locks; review the installed version's behavior. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Prometheus storage](https://prometheus.io/docs/prometheus/latest/storage/) | Review retention, local storage, and durability considerations for metrics infrastructure. | Advanced; public reference. Persistent storage is not a substitute for monitoring continuity or an exercised restore. |
| [Thanos documentation](https://thanos.io/tip/thanos/getting-started.md/) | Compare a distributed metrics architecture and its component responsibilities. | Advanced; public project guide. The tip documentation can describe development features; select a matching release. |
| [VictoriaMetrics documentation](https://docs.victoriametrics.com/) | Compare documented metrics ingestion, querying, deployment, and operation options. | Intermediate to advanced; public reference collection. Distinguish single-node, cluster, and commercial feature boundaries. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Intermediate; cost work requires billing and usage data, not estimates alone. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |

[Browse the other collections](README.md#resource-collections)

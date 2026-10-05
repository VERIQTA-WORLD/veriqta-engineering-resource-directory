# Scalability engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [Load semantics and acceptance criteria](#load-semantics-and-acceptance-criteria)
- [Resource, scheduling, and scaling behavior](#resource-scheduling-and-scaling-behavior)
- [State and data bottlenecks](#state-and-data-bottlenecks)
- [Traffic and measurement infrastructure](#traffic-and-measurement-infrastructure)

## Load semantics and acceptance criteria

Use rate, task, threshold, and generator documentation to describe the experiment. Report useful throughput and latency with errors, rather than throughput alone.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [k6 arrival-rate executors](https://grafana.com/docs/k6/latest/using-k6/scenarios/concepts/arrival-rate-vu-allocation/) | Understand workload generation and virtual-user allocation for arrival-rate tests. | Intermediate; public reference. Generator capacity and dropped iterations can distort the apparent system limit. |
| [k6 thresholds](https://grafana.com/docs/k6/latest/using-k6/thresholds/) | Define explicit load-test acceptance conditions rather than relying on a completed run. | Intermediate; public reference. Thresholds need a justified target, representative workload, and sufficient observations. |
| [Locust quick start](https://docs.locust.io/en/stable/quickstart.html) | Practice a Python-defined load test using project-maintained setup instructions. | Intermediate; public quick-start guide. The stable URL currently serves a development build; select documentation matching the installed Locust version and use authorized targets. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. |
| [sysbench](https://github.com/akopytov/sysbench) | Compare system and database benchmarking workloads in a controllable test environment. | Intermediate; public project repository. Benchmarks can saturate resources or alter test data; isolate targets. |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. |

## Resource, scheduling, and scaling behavior

Read the implementation's resource and scaling semantics, including limits and provider supply. Review disruption and startup effects during scale events.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes horizontal pod autoscaling](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/) | Study metric-based workload scaling and controller behavior. | Intermediate; public reference. Scaling replicas does not necessarily resolve a dependency bottleneck or supply node capacity. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Intermediate; a disruption budget is not a universal guarantee against outages. |
| [KEDA documentation](https://keda.sh/docs/) | Evaluate event-driven workload autoscaling and its external metric dependencies. | Intermediate; public versioned project documentation. Scaling cannot repair slow dependencies or supply unavailable infrastructure capacity. |
| [Kubernetes Vertical Pod Autoscaler](https://github.com/kubernetes/autoscaler/tree/master/vertical-pod-autoscaler) | Review resource recommendation and adjustment workflows for Kubernetes workloads. | Advanced; public project repository. Resource updates can affect scheduling and availability; check the selected update mode. |
| [Kubernetes Cluster Autoscaler](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler) | Review node-capacity scaling and provider integration constraints. | Advanced; public project repository. Provider quotas, node-group limits, and workload scheduling constraints affect expansion. |
| [Karpenter documentation](https://karpenter.sh/docs/) | Compare node provisioning and disruption behavior for supported Kubernetes environments. | Advanced; public project documentation. Provider compatibility, IAM permissions, quotas, and replacement effects require review. |
| [Linux control group v2 documentation](https://docs.kernel.org/admin-guide/cgroup-v2.html) | Understand hierarchical host resource control and interactions with service managers and container runtimes. | Advanced; public kernel reference tracking a development kernel at review time. Match the deployed kernel and verify cgroup mode and delegated permissions before experiments. |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |
| [Amazon EC2 Auto Scaling documentation](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) | Review instance-group scaling, health, and fleet operating behavior. | Intermediate; public reference. Scaling policies need capacity, permissions, startup time, and cost review. |
| [Azure Virtual Machine Scale Sets documentation](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/) | Find fleet scaling, configuration, upgrade, and operations guidance. | Intermediate; public reference collection. Check orchestration mode and the deployed image and service versions. |
| [Google Cloud managed instance groups](https://cloud.google.com/compute/docs/instance-groups) | Review VM group management, health, and scaling guidance. | Intermediate; public reference. Regional capacity, quotas, startup time, and managed-group configuration affect outcomes. |

## State and data bottlenecks

Use plans, locks, maintenance, replication, and coordination guidance to understand why a data path scales as observed.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL EXPLAIN guidance](https://www.postgresql.org/docs/current/using-explain.html) | Read execution plans and investigate query behavior with documented planner concepts. | Intermediate; public guide. EXPLAIN ANALYZE executes the query; use controlled targets for statements with side effects. |
| [PostgreSQL explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html) | Understand lock conflicts and deadlock behavior before intervening in blocked database work. | Intermediate; public reference. Terminating a session can abort transactions and affect application behavior. |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [PostgreSQL routine vacuuming](https://www.postgresql.org/docs/current/routine-vacuuming.html) | Investigate maintenance, dead tuples, statistics, and transaction-ID safety concerns. | Intermediate; public guide. Maintenance changes can affect I/O and locks; review the installed version's behavior. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [MySQL Performance Schema](https://dev.mysql.com/doc/refman/8.4/en/performance-schema.html) | Investigate instrumented database execution and resource use through the supported diagnostic system. | Advanced; public version-specific reference. Instrumentation, privileges, and overhead need review. |
| [MySQL replication reference](https://dev.mysql.com/doc/refman/8.4/en/replication.html) | Review replication arrangements and failure-sensitive operating behavior. | Advanced; public manual. Replication consistency and recovery depend on the chosen configuration and topology. |
| [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/) | Compare persistence modes and their durability and restart implications. | Intermediate; public guide. Persisted data and replicas are not proof of tested recovery or acceptable data loss. |
| [Apache Kafka operations documentation](https://kafka.apache.org/43/operations/) | Review messaging durability, replication, configuration, and operating interfaces. | Advanced; public Apache project documentation for Kafka 4.3. Select the deployed version; broker, client, storage, and coordination changes require separate review. |
| [Apache Cassandra documentation](https://cassandra.apache.org/doc/latest/) | Explore distributed database architecture, repair, consistency, and operations. | Advanced; public project documentation. Use the deployed release; replica health and consistency choices affect reads, writes, and repair. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |

## Traffic and measurement infrastructure

Review load distribution, proxy behavior, instrumentation aggregation, and telemetry storage. Poorly defined metrics can obscure an uneven workload distribution.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Load balancing at the frontend](https://sre.google/sre-book/load-balancing-frontend/) | Explore traffic distribution and frontend reliability across infrastructure boundaries. | Advanced; public chapter. Provider and network topology determine which mechanisms are available. |
| [Load balancing in the datacenter](https://sre.google/sre-book/load-balancing-datacenter/) | Compare service load-balancing behavior, health signals, and backend selection. | Advanced; public chapter. A healthy endpoint may still be unable to satisfy the requested operation. |
| [HAProxy configuration manuals](https://docs.haproxy.org/) | Find versioned proxy, routing, health-check, and operational references. | Intermediate to advanced; public manual collection. Select the installed release and review connection, timeout, and retry interactions. |
| [NGINX documentation](https://nginx.org/en/docs/) | Review proxy, upstream, request processing, logging, and network configuration references. | Intermediate; public documentation. Open-source and commercial capabilities differ; select the correct product and version. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Prometheus storage](https://prometheus.io/docs/prometheus/latest/storage/) | Review retention, local storage, and durability considerations for metrics infrastructure. | Advanced; public reference. Persistent storage is not a substitute for monitoring continuity or an exercised restore. |
| [Prometheus instrumentation practices](https://prometheus.io/docs/practices/instrumentation/) | Select metrics and labels that answer operating questions without uncontrolled cardinality. | Intermediate; public guide. Instrumentation overhead and confidential label values need review. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |

[Browse the other collections](README.md#resource-collections)

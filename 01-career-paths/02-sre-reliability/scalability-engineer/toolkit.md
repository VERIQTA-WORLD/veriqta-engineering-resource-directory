# Scalability engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Load and workload modeling](#load-and-workload-modeling)
- [Profiling and resource diagnosis](#profiling-and-resource-diagnosis)
- [Elastic compute and scheduling](#elastic-compute-and-scheduling)
- [Data, coordination, and traffic distribution](#data-coordination-and-traffic-distribution)
- [Telemetry scale and economic evidence](#telemetry-scale-and-economic-evidence)

## Load and workload modeling

Match arrival behavior, concurrency, transaction mix, and data distribution to the real workload. Check the load generator before attributing a plateau to the system.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. |
| [sysbench](https://github.com/akopytov/sysbench) | Compare system and database benchmarking workloads in a controllable test environment. | Intermediate; public project repository. Benchmarks can saturate resources or alter test data; isolate targets. |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |

## Profiling and resource diagnosis

Investigate bottlenecks at the affected layer. Resource counters, flame graphs, database statistics, and packet measurements have different overhead and attribution limits.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |
| [BCC tools and examples](https://github.com/iovisor/bcc) | Explore eBPF-based tracing utilities for investigating operating-system behavior. | Advanced; public project repository. Tool support depends on kernel and build requirements; review privileges and collection overhead. |
| [bpftrace source and documentation](https://github.com/bpftrace/bpftrace) | Read tracing-language references and project guidance for Linux investigations. | Advanced; public tracing-language repository. Check release-specific language support, kernel requirements, privileges, and collection overhead. |
| [Parca documentation](https://www.parca.dev/docs/overview/) | Explore continuous profiling for investigating resource consumption over time. | Advanced; public project documentation. Collection permissions, symbolization, and profile storage need review. |
| [Prometheus Node Exporter](https://github.com/prometheus/node_exporter) | Collect host metrics for resource pressure and infrastructure monitoring. | Intermediate; public project repository. Review enabled collectors, privileges, and host access boundaries. |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. The linked manual currently displays development version 4.7.4; match the installed release. |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [MySQL Performance Schema](https://dev.mysql.com/doc/refman/8.4/en/performance-schema.html) | Investigate instrumented database execution and resource use through the supported diagnostic system. | Advanced; public version-specific reference. Instrumentation, privileges, and overhead need review. |

## Elastic compute and scheduling

Compare workload, pod, node, and VM scaling controls. Check supply limits, placement, initialization, stability, and cost before relying on elasticity.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [KEDA documentation](https://keda.sh/docs/) | Evaluate event-driven workload autoscaling and its external metric dependencies. | Intermediate; public versioned project documentation. Scaling cannot repair slow dependencies or supply unavailable infrastructure capacity. |
| [Kubernetes Vertical Pod Autoscaler](https://github.com/kubernetes/autoscaler/tree/master/vertical-pod-autoscaler) | Review resource recommendation and adjustment workflows for Kubernetes workloads. | Advanced; public project repository. Resource updates can affect scheduling and availability; check the selected update mode. |
| [Kubernetes Cluster Autoscaler](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler) | Review node-capacity scaling and provider integration constraints. | Advanced; public project repository. Provider quotas, node-group limits, and workload scheduling constraints affect expansion. |
| [Karpenter documentation](https://karpenter.sh/docs/) | Compare node provisioning and disruption behavior for supported Kubernetes environments. | Advanced; public project documentation. Provider compatibility, IAM permissions, quotas, and replacement effects require review. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Amazon EC2 Auto Scaling documentation](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) | Review instance-group scaling, health, and fleet operating behavior. | Intermediate; public reference. Scaling policies need capacity, permissions, startup time, and cost review. |
| [Azure Virtual Machine Scale Sets documentation](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/) | Find fleet scaling, configuration, upgrade, and operations guidance. | Intermediate; public reference collection. Check orchestration mode and the deployed image and service versions. |
| [Google Cloud managed instance groups](https://cloud.google.com/compute/docs/instance-groups) | Review VM group management, health, and scaling guidance. | Intermediate; public reference. Regional capacity, quotas, startup time, and managed-group configuration affect outcomes. |

## Data, coordination, and traffic distribution

Compare persistence, replication, partitioning, connection, and routing mechanisms in the context of the actual workload. Adding nodes can introduce coordination and operational costs.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL documentation](https://www.postgresql.org/docs/current/) | Locate administration, SQL, replication, security, and operating references for PostgreSQL. | Foundation onward; public documentation. The current alias tracks a changing major version; use the manual for the installed server. |
| [MySQL reference manual](https://dev.mysql.com/doc/refman/8.4/en/) | Find database administration, InnoDB, replication, security, and recovery references. | Intermediate; public version-specific manual for MySQL 8.4. Use the manual matching the deployed release. |
| [Redis documentation](https://redis.io/docs/latest/) | Find command, deployment, persistence, replication, and operating references for Redis products. | Foundation onward; public documentation. Distinguish product editions and deployment models; review applicable terms separately. |
| [MongoDB self-managed operations checklist](https://www.mongodb.com/docs/manual/administration/production-checklist-operations/) | Review operational considerations for a MongoDB deployment. | Intermediate to advanced; public checklist for self-managed deployments. Managed-service responsibilities and deployment-specific limits differ. |
| [Apache Kafka operations documentation](https://kafka.apache.org/43/operations/) | Review messaging durability, replication, configuration, and operating interfaces. | Advanced; public Apache project documentation for Kafka 4.3. Select the deployed version; broker, client, storage, and coordination changes require separate review. |
| [Apache Cassandra documentation](https://cassandra.apache.org/doc/latest/) | Explore distributed database architecture, repair, consistency, and operations. | Advanced; public project documentation. Use the deployed release; replica health and consistency choices affect reads, writes, and repair. |
| [etcd documentation](https://etcd.io/docs/) | Review distributed coordination, maintenance, recovery, and failure behavior. | Advanced; public versioned reference collection. Quorum, disk latency, and recovery state need explicit operating plans. |
| [PgBouncer documentation](https://www.pgbouncer.org/config.html) | Compare connection pooling behavior, resource settings, and application compatibility. | Intermediate; public configuration reference. Pooling mode and session-dependent application features affect correctness. |
| [HAProxy configuration manuals](https://docs.haproxy.org/) | Find versioned proxy, routing, health-check, and operational references. | Intermediate to advanced; public manual collection. Select the installed release and review connection, timeout, and retry interactions. |
| [NGINX documentation](https://nginx.org/en/docs/) | Review proxy, upstream, request processing, logging, and network configuration references. | Intermediate; public documentation. Open-source and commercial capabilities differ; select the correct product and version. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |

## Telemetry scale and economic evidence

Telemetry systems also have cardinality, ingest, query, retention, and recovery constraints. Connect cost allocation to observed usage and service outcomes.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Thanos documentation](https://thanos.io/tip/thanos/getting-started.md/) | Compare a distributed metrics architecture and its component responsibilities. | Advanced; public project guide. The tip documentation can describe development features; select a matching release. |
| [VictoriaMetrics documentation](https://docs.victoriametrics.com/) | Compare documented metrics ingestion, querying, deployment, and operation options. | Intermediate to advanced; public reference collection. Distinguish single-node, cluster, and commercial feature boundaries. |
| [kube-state-metrics](https://github.com/kubernetes/kube-state-metrics) | Observe Kubernetes object state alongside workload and node performance metrics. | Intermediate; public project repository. Object-state metrics do not replace application-level service indicators. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |
| [Sloth](https://sloth.dev/) | Compare an SLO-to-Prometheus rule generator for service monitoring workflows. | Intermediate; public project documentation. Correct generated rules still require valid indicators and label boundaries. |
| [Pyrra](https://github.com/pyrra-dev/pyrra) | Evaluate SLO definition and visualization tooling around Prometheus-based measurements. | Intermediate; public project repository. Review deployment requirements and the service's actual measurement coverage. |

[Browse the other collections](README.md#resource-collections)

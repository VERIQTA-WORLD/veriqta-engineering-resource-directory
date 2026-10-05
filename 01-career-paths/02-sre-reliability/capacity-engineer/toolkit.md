# Capacity engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Demand and service measurements](#demand-and-service-measurements)
- [Load generators and workload checks](#load-generators-and-workload-checks)
- [Host and runtime diagnosis](#host-and-runtime-diagnosis)
- [Elastic capacity controls](#elastic-capacity-controls)
- [Metrics infrastructure and economic review](#metrics-infrastructure-and-economic-review)

## Demand and service measurements

Use observed traffic and service outcomes alongside resource measurements. A dashboard with spare CPU does not prove that storage, connections, or a dependency can absorb more demand.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus Node Exporter](https://github.com/prometheus/node_exporter) | Collect host metrics for resource pressure and infrastructure monitoring. | Intermediate; public project repository. Review enabled collectors, privileges, and host access boundaries. |
| [kube-state-metrics](https://github.com/kubernetes/kube-state-metrics) | Observe Kubernetes object state alongside workload and node performance metrics. | Intermediate; public project repository. Object-state metrics do not replace application-level service indicators. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Sloth](https://sloth.dev/) | Compare an SLO-to-Prometheus rule generator for service monitoring workflows. | Intermediate; public project documentation. Correct generated rules still require valid indicators and label boundaries. |
| [Pyrra](https://github.com/pyrra-dev/pyrra) | Evaluate SLO definition and visualization tooling around Prometheus-based measurements. | Intermediate; public project repository. Review deployment requirements and the service's actual measurement coverage. |

## Load generators and workload checks

Compare arrival rate, concurrency, task mix, test data, and generator limits. Select a tool around the workload you need to reproduce.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |
| [sysbench](https://github.com/akopytov/sysbench) | Compare system and database benchmarking workloads in a controllable test environment. | Intermediate; public project repository. Benchmarks can saturate resources or alter test data; isolate targets. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |

## Host and runtime diagnosis

Use profiles and resource evidence to identify the bottleneck before buying capacity. Collection overhead and privilege requirements vary by tool.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |
| [BCC tools and examples](https://github.com/iovisor/bcc) | Explore eBPF-based tracing utilities for investigating operating-system behavior. | Advanced; public project repository. Tool support depends on kernel and build requirements; review privileges and collection overhead. |
| [bpftrace source and documentation](https://github.com/bpftrace/bpftrace) | Read tracing-language references and project guidance for Linux investigations. | Advanced; public tracing-language repository. Check release-specific language support, kernel requirements, privileges, and collection overhead. |
| [Parca documentation](https://www.parca.dev/docs/overview/) | Explore continuous profiling for investigating resource consumption over time. | Advanced; public project documentation. Collection permissions, symbolization, and profile storage need review. |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. The linked manual currently displays development version 4.7.4; match the installed release. |
| [jq manual](https://jqlang.org/manual/) | Inspect and transform JSON returned by command-line clients and infrastructure APIs. | Foundation onward; publicly readable manual. Validate missing fields rather than assuming one provider response shape. |
| [Python tutorial](https://docs.python.org/3/tutorial/) | Read the language tutorial before maintaining automation that parses data, calls services, or manages files. | Foundation in Python; assumes basic programming knowledge. Publicly readable; use an isolated virtual environment and match the installed interpreter. |

## Elastic capacity controls

Pod, node, event-driven, and VM scaling operate at different layers. Check limits, placement, startup time, availability, and cost before relying on automatic expansion.

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

## Metrics infrastructure and economic review

Telemetry capacity and retention also need a model. Separate a proposed cost estimate from actual allocation and measured usage.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Thanos documentation](https://thanos.io/tip/thanos/getting-started.md/) | Compare a distributed metrics architecture and its component responsibilities. | Advanced; public project guide. The tip documentation can describe development features; select a matching release. |
| [VictoriaMetrics documentation](https://docs.victoriametrics.com/) | Compare documented metrics ingestion, querying, deployment, and operation options. | Intermediate to advanced; public reference collection. Distinguish single-node, cluster, and commercial feature boundaries. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |

[Browse the other collections](README.md#resource-collections)

# Network reliability engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Packet, path, and throughput diagnosis](#packet-path-and-throughput-diagnosis)
- [Routing and network inventory](#routing-and-network-inventory)
- [DNS and name resolution](#dns-and-name-resolution)
- [Traffic distribution and cluster data paths](#traffic-distribution-and-cluster-data-paths)
- [Telemetry and controlled fault environments](#telemetry-and-controlled-fault-environments)

## Packet, path, and throughput diagnosis

Choose observation points and authorized targets before collecting evidence. ICMP behavior and intermediate-hop results do not necessarily explain application traffic.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. The linked manual currently displays development version 4.7.4; match the installed release. |
| [tcpdump and libpcap](https://www.tcpdump.org/) | Find packet-capture utilities and official manual navigation. | Intermediate; public project site. Capture permissions, sensitive payloads, retention, and observation location require review. |
| [mtr project](https://github.com/traviscross/mtr) | Compare repeated route and response measurements when investigating reachability or latency. | Intermediate; public project repository. Intermediate-hop loss does not necessarily mean loss of end-to-end application traffic. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [curl documentation](https://curl.se/docs/) | Find official command-line, protocol, TLS, and library references for HTTP and other supported transfers. | Foundation onward; public reference collection. Inspect quoting, output, certificates, and failure behavior before using curl in automation. |

## Routing and network inventory

Review routing policy and the intended topology alongside effective device state. A source-of-truth model must be kept synchronized with real changes.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [FRRouting documentation](https://docs.frrouting.org/en/latest/) | Review routing daemons, protocol configuration, and routing diagnostics. | Advanced; public reference. Routing changes can disrupt connectivity; use a controlled topology and matching software version. |
| [BIRD documentation](https://bird.network.cz/?get_doc&f=bird.html) | Compare a routing daemon's configuration and protocol operating model. | Advanced; public routing-daemon guide for BIRD 2.16.1. Match the deployed release; route changes require isolation and a recovery plan. |
| [NetBox documentation](https://netbox.readthedocs.io/en/stable/) | Explore network inventory and source-of-truth modeling for operational coordination. | Intermediate; public project documentation. Inventory correctness and change synchronization remain organizational responsibilities. |
| [containerlab documentation](https://containerlab.dev/) | Build isolated container-based network topologies for configuration and failure experiments. | Advanced; public project documentation. Network OS images have separate access and licensing requirements; destroy lab topologies and inspect retained files afterward. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Python tutorial](https://docs.python.org/3/tutorial/) | Read the language tutorial before maintaining automation that parses data, calls services, or manages files. | Foundation in Python; assumes basic programming knowledge. Publicly readable; use an isolated virtual environment and match the installed interpreter. |
| [jq manual](https://jqlang.org/manual/) | Inspect and transform JSON returned by command-line clients and infrastructure APIs. | Foundation onward; publicly readable manual. Validate missing fields rather than assuming one provider response shape. |

## DNS and name resolution

Compare resolver and authoritative responsibilities. Cache, validation, forwarding, and service discovery failures can produce different symptoms.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [BIND 9 documentation](https://bind9.readthedocs.io/en/latest/) | Investigate authoritative and recursive DNS configuration and operating behavior. | Advanced; public DNS server manual. The latest URL currently serves development documentation; select a release matching the deployed BIND version. |
| [Unbound documentation](https://unbound.docs.nlnetlabs.nl/en/latest/) | Explore recursive resolver configuration, validation, and operating references. | Intermediate; public project documentation. Trust, forwarding, cache, and access configuration need environment-specific review. |
| [CoreDNS documentation](https://coredns.io/manual/toc/) | Review DNS plugin chains, configuration, and behavior for supported environments. | Intermediate; public project manual. Plugin ordering, caching, and upstream behavior affect resolution. |

## Traffic distribution and cluster data paths

Proxies, gateways, network plugins, and meshes operate at different layers. Identify which component owns the affected path and retry behavior.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [HAProxy configuration manuals](https://docs.haproxy.org/) | Find versioned proxy, routing, health-check, and operational references. | Intermediate to advanced; public manual collection. Select the installed release and review connection, timeout, and retry interactions. |
| [NGINX documentation](https://nginx.org/en/docs/) | Review proxy, upstream, request processing, logging, and network configuration references. | Intermediate; public documentation. Open-source and commercial capabilities differ; select the correct product and version. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Intermediate; APIs require a compatible implementation. Check conformance and feature status. |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Calico](https://docs.tigera.io/calico/latest/about/) | Compare Kubernetes networking and network-policy approaches. | Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |

## Telemetry and controlled fault environments

Correlate network measurements with useful application outcomes. A fault experiment or load generator can itself overload the path.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Sloth](https://sloth.dev/) | Compare an SLO-to-Prometheus rule generator for service monitoring workflows. | Intermediate; public project documentation. Correct generated rules still require valid indicators and label boundaries. |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |
| [Chaos Mesh](https://chaos-mesh.org/docs/) | Explore Kubernetes failure-injection experiments. | Advanced; use isolated environments and bounded experiments before considering production use. |

[Browse the other collections](README.md#resource-collections)

# Network reliability engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [Capture and protocol references](#capture-and-protocol-references)
- [Routing and DNS behavior](#routing-and-dns-behavior)
- [Cloud and cluster networking](#cloud-and-cluster-networking)
- [Proxy and observation behavior](#proxy-and-observation-behavior)

## Capture and protocol references

Use the capture manual and protocol semantics together. Restrict sensitive data collection and record the interfaces, timing, and filters used.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Wireshark user guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Review capture setup, protocol analysis, display filtering, and packet inspection workflows. | Foundation to advanced; public manual currently displaying development version 4.7.4. Match the installed release; packet capture requires permission and careful handling of sensitive data. |
| [tcpdump manual](https://www.tcpdump.org/manpages/tcpdump.1.html) | Check capture expressions, interface selection, output, and diagnostic options. | Intermediate; public CLI reference. Restrict collection to authorized traffic and define secure capture-file retention. |
| [TCP specification, RFC 9293](https://www.rfc-editor.org/rfc/rfc9293.html) | Review TCP transport semantics relevant to connection and retransmission investigations. | Advanced; public specification. The network path and application protocol add behavior beyond TCP. |
| [QUIC transport, RFC 9000](https://www.rfc-editor.org/rfc/rfc9000.html) | Review transport behavior relevant to modern HTTP and connection investigations. | Advanced; public specification. Use application and implementation references alongside the transport document. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Advanced; certificate lifecycle and application configuration require additional guidance. |
| [IP performance metrics framework, RFC 2330](https://www.rfc-editor.org/rfc/rfc2330.html) | Distinguish measurement definitions, samples, and network performance methodology. | Advanced; public foundational framework. Measurement location and sampling design affect interpretation. |

## Routing and DNS behavior

Match software versions, routing policy, DNS roles, caches, and validation before corrective changes.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [FRRouting documentation](https://docs.frrouting.org/en/latest/) | Review routing daemons, protocol configuration, and routing diagnostics. | Advanced; public reference. Routing changes can disrupt connectivity; use a controlled topology and matching software version. |
| [BIRD documentation](https://bird.network.cz/?get_doc&f=bird.html) | Compare a routing daemon's configuration and protocol operating model. | Advanced; public routing-daemon guide for BIRD 2.16.1. Match the deployed release; route changes require isolation and a recovery plan. |
| [BIND 9 documentation](https://bind9.readthedocs.io/en/latest/) | Investigate authoritative and recursive DNS configuration and operating behavior. | Advanced; public DNS server manual. The latest URL currently serves development documentation; select a release matching the deployed BIND version. |
| [Unbound documentation](https://unbound.docs.nlnetlabs.nl/en/latest/) | Explore recursive resolver configuration, validation, and operating references. | Intermediate; public project documentation. Trust, forwarding, cache, and access configuration need environment-specific review. |
| [CoreDNS documentation](https://coredns.io/manual/toc/) | Review DNS plugin chains, configuration, and behavior for supported environments. | Intermediate; public project manual. Plugin ordering, caching, and upstream behavior affect resolution. |
| [DNS concepts, RFC 1034](https://www.rfc-editor.org/rfc/rfc1034.html) | Read foundational DNS concepts and name-resolution responsibilities. | Advanced; public foundational RFC. Later documents update parts of DNS behavior; consult relevant implementation and update references. |
| [DNSSEC introduction, RFC 4033](https://www.rfc-editor.org/rfc/rfc4033.html) | Understand DNS authentication concepts and boundaries when investigating validation failures. | Advanced; public RFC. DNSSEC authenticates DNS data; it is not transport encryption or general application authorization. |
| [BGP-4, RFC 4271](https://www.rfc-editor.org/rfc/rfc4271.html) | Review BGP route exchange and decision behavior alongside implementation manuals. | Advanced; public RFC. Later RFCs extend and update the protocol; operational policy is environment-specific. |

## Cloud and cluster networking

Inspect the actual route, policy, resolver, service endpoints, and provider boundary. A configured object does not prove the intended traffic can pass.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS networking architecture guidance](https://aws.amazon.com/architecture/networking-content-delivery/) | Find provider architecture references for network connectivity and traffic delivery. | Intermediate; public discovery collection. Review a selected design separately; service charges and regional constraints vary. |
| [Azure networking documentation](https://learn.microsoft.com/en-us/azure/networking/) | Find provider-specific connectivity, routing, DNS, and network operating references. | Intermediate; public documentation collection. Select the service used by the workload; diagrams do not prove effective routing or policy. |
| [Google Cloud VPC documentation](https://cloud.google.com/vpc/docs) | Review virtual-network, routing, firewall, and connectivity behavior. | Intermediate; public provider reference. Default and effective policies must be inspected in the actual project. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Kubernetes DNS troubleshooting](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/) | Investigate workload DNS resolution through documented cluster diagnostic steps. | Intermediate; public task guide. Distinguish pod, service, resolver, and upstream failures; some steps create diagnostic workloads. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Intermediate; APIs require a compatible implementation. Check conformance and feature status. |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Calico](https://docs.tigera.io/calico/latest/about/) | Compare Kubernetes networking and network-policy approaches. | Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility. |

## Proxy and observation behavior

Review timeouts, health checks, connection handling, probe location, and telemetry aggregation for the real path.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [HAProxy configuration manuals](https://docs.haproxy.org/) | Find versioned proxy, routing, health-check, and operational references. | Intermediate to advanced; public manual collection. Select the installed release and review connection, timeout, and retry interactions. |
| [NGINX documentation](https://nginx.org/en/docs/) | Review proxy, upstream, request processing, logging, and network configuration references. | Intermediate; public documentation. Open-source and commercial capabilities differ; select the correct product and version. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Prometheus instrumentation practices](https://prometheus.io/docs/practices/instrumentation/) | Select metrics and labels that answer operating questions without uncontrolled cardinality. | Intermediate; public guide. Instrumentation overhead and confidential label values need review. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |

[Browse the other collections](README.md#resource-collections)

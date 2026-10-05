# Network reliability engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Confirm the affected network and service boundary](#confirm-the-affected-network-and-service-boundary)
- [Investigate routing, DNS, and traffic behavior](#investigate-routing-dns-and-traffic-behavior)
- [Validate changes and failure containment](#validate-changes-and-failure-containment)
- [Keep measurements, authority, and incident evidence](#keep-measurements-authority-and-incident-evidence)

## Confirm the affected network and service boundary

Correlate user symptoms, probe location, capture evidence, endpoint behavior, and recent changes. Avoid equating one failed probe with a global outage.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Wireshark user guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Review capture setup, protocol analysis, display filtering, and packet inspection workflows. | Foundation to advanced; public manual currently displaying development version 4.7.4. Match the installed release; packet capture requires permission and careful handling of sensitive data. |
| [tcpdump manual](https://www.tcpdump.org/manpages/tcpdump.1.html) | Check capture expressions, interface selection, output, and diagnostic options. | Intermediate; public CLI reference. Restrict collection to authorized traffic and define secure capture-file retention. |
| [mtr project](https://github.com/traviscross/mtr) | Compare repeated route and response measurements when investigating reachability or latency. | Intermediate; public project repository. Intermediate-hop loss does not necessarily mean loss of end-to-end application traffic. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |

## Investigate routing, DNS, and traffic behavior

Trace the effective route and resolution path, then check the proxy or gateway layer. Review cache and timeout behavior before broad configuration changes.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [FRRouting documentation](https://docs.frrouting.org/en/latest/) | Review routing daemons, protocol configuration, and routing diagnostics. | Advanced; public reference. Routing changes can disrupt connectivity; use a controlled topology and matching software version. |
| [BIRD documentation](https://bird.network.cz/?get_doc&f=bird.html) | Compare a routing daemon's configuration and protocol operating model. | Advanced; public routing-daemon guide for BIRD 2.16.1. Match the deployed release; route changes require isolation and a recovery plan. |
| [BIND 9 documentation](https://bind9.readthedocs.io/en/latest/) | Investigate authoritative and recursive DNS configuration and operating behavior. | Advanced; public DNS server manual. The latest URL currently serves development documentation; select a release matching the deployed BIND version. |
| [Unbound documentation](https://unbound.docs.nlnetlabs.nl/en/latest/) | Explore recursive resolver configuration, validation, and operating references. | Intermediate; public project documentation. Trust, forwarding, cache, and access configuration need environment-specific review. |
| [Kubernetes DNS troubleshooting](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/) | Investigate workload DNS resolution through documented cluster diagnostic steps. | Intermediate; public task guide. Distinguish pod, service, resolver, and upstream failures; some steps create diagnostic workloads. |
| [HAProxy configuration manuals](https://docs.haproxy.org/) | Find versioned proxy, routing, health-check, and operational references. | Intermediate to advanced; public manual collection. Select the installed release and review connection, timeout, and retry interactions. |
| [NGINX documentation](https://nginx.org/en/docs/) | Review proxy, upstream, request processing, logging, and network configuration references. | Intermediate; public documentation. Open-source and commercial capabilities differ; select the correct product and version. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |

## Validate changes and failure containment

Test intended forwarding, isolation, service discovery, and recovery in a controlled topology before production rollout. Preserve the previous configuration and a usable recovery path.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [containerlab quick start](https://containerlab.dev/quickstart/) | Practice a documented local topology deployment and inspection workflow. | Intermediate; public local topology lab. Requires a supported Linux environment and container runtime; the Arista cEOS example image requires a vendor account and separate download. |
| [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) | Review simulated changes and configuration differences before a deployment. | Intermediate; public reference. Module support varies, explicit task settings can allow changes, and diff output may expose secrets. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Advanced; official PDF. Application and schema compatibility must be tested in your own system. |

## Keep measurements, authority, and incident evidence

Protect packet data, define access and retention, and connect network measurements to user outcomes and incident learning.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [IP performance metrics framework, RFC 2330](https://www.rfc-editor.org/rfc/rfc2330.html) | Distinguish measurement definitions, samples, and network performance methodology. | Advanced; public foundational framework. Measurement location and sampling design affect interpretation. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Cloudflare outage of July 2, 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/) | Read the original account of a globally propagated service failure and its operating lessons. | Intermediate; public historical incident report. Retain the documented cause and timeline; it does not describe every later system version. |
| [Cloudflare control-plane and analytics outage](https://blog.cloudflare.com/post-mortem-on-cloudflare-control-plane-and-analytics-outage/) | Compare dependency, datacenter, and recovery concerns in an original outage account. | Advanced; public historical postmortem. Distinguish affected control-plane and analytics functions from unaffected services. |

[Browse the other collections](README.md#resource-collections)

# Network reliability engineer: related careers

[Career overview](README.md) · [SRE and reliability directory](../README.md)

These collections overlap in reliability concerns but emphasize different engineering boundaries. Role ownership varies by organization; use the scope descriptions to find the resources you need.

## Adjacent resource collections

| Career | Distinct emphasis and overlap | Collection status |
| --- | --- | --- |
| [Service reliability engineer](../service-reliability-engineer/README.md) | Resources for operating an individual service or connected service boundary: user-facing outcomes, dependencies, latency, correctness, change safety, capacity, and recovery. | Included in this folder. |
| [Infrastructure reliability engineer](../infrastructure-reliability-engineer/README.md) | Resources for reliability of compute, hosts, provisioning, storage, networking, and infrastructure control systems. | Included in this folder. |
| [Cloud reliability engineer](../cloud-reliability-engineer/README.md) | Resources for operating reliable cloud workloads across provider health, service limits, identity, networking, scaling, deployment, persistent data, and regional recovery. | Included in this folder. |
| [Capacity engineer](../capacity-engineer/README.md) | Resources for measuring demand, identifying bottlenecks, forecasting resource needs, and validating the capacity available during normal operation and failures. | Included in this folder. |
| [Resilience engineer](../resilience-engineer/README.md) | Resources for preserving useful service during faults and recovering after disruption. | Included in this folder. |

## Shared references

These direct references remain useful when moving between the adjacent collections. Their inclusion does not make the roles interchangeable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Wireshark user guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Review capture setup, protocol analysis, display filtering, and packet inspection workflows. | Foundation to advanced; public manual currently displaying development version 4.7.4. Match the installed release; packet capture requires permission and careful handling of sensitive data. |
| [tcpdump manual](https://www.tcpdump.org/manpages/tcpdump.1.html) | Check capture expressions, interface selection, output, and diagnostic options. | Intermediate; public CLI reference. Restrict collection to authorized traffic and define secure capture-file retention. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. |
| [FRRouting documentation](https://docs.frrouting.org/en/latest/) | Review routing daemons, protocol configuration, and routing diagnostics. | Advanced; public reference. Routing changes can disrupt connectivity; use a controlled topology and matching software version. |
| [Kubernetes DNS troubleshooting](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/) | Investigate workload DNS resolution through documented cluster diagnostic steps. | Intermediate; public task guide. Distinguish pod, service, resolver, and upstream failures; some steps create diagnostic workloads. |

[Browse all 12 SRE and reliability careers](../README.md#career-collections)

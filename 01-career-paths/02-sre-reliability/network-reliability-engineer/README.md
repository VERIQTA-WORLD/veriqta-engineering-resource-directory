# Network reliability engineer

[SRE and reliability directory](../README.md)

Resources for reliable connectivity, routing, DNS, traffic distribution, service discovery, and network-dependent application behavior. The collection connects packet and path evidence to protocol semantics, provider networking, controlled configuration changes, and service-level measurements.

## Find a resource

Use the collections below for the task in front of you. Compare purpose, prerequisites, deployment model, and operating limitations before choosing a tool or applying a guide. The tools are alternatives or complementary components, not a required stack.

## Resource collections

| Collection | What you will find |
| --- | --- |
| [Tool directory](toolkit.md) | Tools grouped by implementation or operating task, with alternatives and selection notes. |
| [Official documentation](official-documentation.md) | Authoritative manuals, API references, and focused operating guides. |
| [Reference architectures and design guidance](reference-architectures.md) | Documented designs, patterns, assumptions, and decision resources. |
| [Learning resources](learning-resources.md) | Books, tutorials, research, talks, and discovery collections by topic. |
| [Labs, examples, and projects](labs-and-projects.md) | Practice environments, examples, workshops, and implementation repositories. |
| [Production responsibilities and operational resources](production-responsibilities.md) | Operating concerns connected to diagnostic, incident, and recovery resources. |
| [Standards and frameworks](standards-and-frameworks.md) | Specifications, security guidance, and review frameworks with scope distinctions. |
| [Related careers](related-careers.md) | Adjacent collections, their overlap, and their development status. |

## Useful starting points

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Wireshark user guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Review capture setup, protocol analysis, display filtering, and packet inspection workflows. | Foundation to advanced; public manual currently displaying development version 4.7.4. Match the installed release; packet capture requires permission and careful handling of sensitive data. |
| [tcpdump manual](https://www.tcpdump.org/manpages/tcpdump.1.html) | Check capture expressions, interface selection, output, and diagnostic options. | Intermediate; public CLI reference. Restrict collection to authorized traffic and define secure capture-file retention. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. |
| [FRRouting documentation](https://docs.frrouting.org/en/latest/) | Review routing daemons, protocol configuration, and routing diagnostics. | Advanced; public reference. Routing changes can disrupt connectivity; use a controlled topology and matching software version. |
| [Kubernetes DNS troubleshooting](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/) | Investigate workload DNS resolution through documented cluster diagnostic steps. | Intermediate; public task guide. Distinguish pod, service, resolver, and upstream failures; some steps create diagnostic workloads. |

## Coverage

- Reachability, latency, loss and observation points.
- Routing and failure convergence.
- DNS, resolver and validation failures.
- Packet capture and protocol interpretation.
- Proxies, health checks and traffic steering.
- Cloud and cluster network dependencies.
- Network change validation, fault tests and service objectives.

## Reading and access

Foundation material assumes limited topic experience; intermediate material usually assumes basic implementation knowledge; advanced material often assumes practical systems or production experience. Each entry narrows those expectations where needed. Publicly readable instructions do not make a hosted service, commercial book, software license, or cloud experiment free.

Resource descriptions and destinations were reviewed on **5 October 2026**. Version, preview, development, and historical notes identify material that needs particular care. The linked manuals and collections are not claimed to have been read or tested in full. External links are used while repository resource IDs and canonical mappings remain unassigned.

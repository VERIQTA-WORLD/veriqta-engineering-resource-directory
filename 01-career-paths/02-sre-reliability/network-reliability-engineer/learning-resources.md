# Network reliability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Protocols and practical analysis](#protocols-and-practical-analysis)
- [Reliability and troubleshooting](#reliability-and-troubleshooting)
- [Original failures and broader discovery](#original-failures-and-broader-discovery)

## Protocols and practical analysis

Use specifications alongside implementation manuals. Reading a protocol document does not establish expertise with the deployed network OS.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [TCP specification, RFC 9293](https://www.rfc-editor.org/rfc/rfc9293.html) | Review TCP transport semantics relevant to connection and retransmission investigations. | Advanced; public specification. The network path and application protocol add behavior beyond TCP. |
| [DNS concepts, RFC 1034](https://www.rfc-editor.org/rfc/rfc1034.html) | Read foundational DNS concepts and name-resolution responsibilities. | Advanced; public foundational RFC. Later documents update parts of DNS behavior; consult relevant implementation and update references. |
| [BGP-4, RFC 4271](https://www.rfc-editor.org/rfc/rfc4271.html) | Review BGP route exchange and decision behavior alongside implementation manuals. | Advanced; public RFC. Later RFCs extend and update the protocol; operational policy is environment-specific. |
| [DNSSEC introduction, RFC 4033](https://www.rfc-editor.org/rfc/rfc4033.html) | Understand DNS authentication concepts and boundaries when investigating validation failures. | Advanced; public RFC. DNSSEC authenticates DNS data; it is not transport encryption or general application authorization. |
| [QUIC transport, RFC 9000](https://www.rfc-editor.org/rfc/rfc9000.html) | Review transport behavior relevant to modern HTTP and connection investigations. | Advanced; public specification. Use application and implementation references alongside the transport document. |
| [Wireshark user guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Review capture setup, protocol analysis, display filtering, and packet inspection workflows. | Foundation to advanced; public manual currently displaying development version 4.7.4. Match the installed release; packet capture requires permission and careful handling of sensitive data. |
| [FRRouting documentation](https://docs.frrouting.org/en/latest/) | Review routing daemons, protocol configuration, and routing diagnostics. | Advanced; public reference. Routing changes can disrupt connectivity; use a controlled topology and matching software version. |

## Reliability and troubleshooting

Apply hypothesis-driven diagnosis to the full request path and its control dependencies rather than assuming every timeout is a packet-loss problem.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |
| [Load balancing at the frontend](https://sre.google/sre-book/load-balancing-frontend/) | Explore traffic distribution and frontend reliability across infrastructure boundaries. | Advanced; public chapter. Provider and network topology determine which mechanisms are available. |
| [Load balancing in the datacenter](https://sre.google/sre-book/load-balancing-datacenter/) | Compare service load-balancing behavior, health signals, and backend selection. | Advanced; public chapter. A healthy endpoint may still be unable to satisfy the requested operation. |
| [Google SRE Workbook: managing load](https://sre.google/workbook/managing-load/) | Connect load balancing, overload management, and failure handling to service behavior. | Intermediate; public chapter. Adapt the examples to local traffic, dependencies, and recovery constraints. |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |

## Original failures and broader discovery

Use historical reports to explore configuration propagation and dependency failures without inventing incident causes.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Cloudflare outage of July 2, 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/) | Read the original account of a globally propagated service failure and its operating lessons. | Intermediate; public historical incident report. Retain the documented cause and timeline; it does not describe every later system version. |
| [Cloudflare control-plane and analytics outage](https://blog.cloudflare.com/post-mortem-on-cloudflare-control-plane-and-analytics-outage/) | Compare dependency, datacenter, and recovery concerns in an original outage account. | Advanced; public historical postmortem. Distinguish affected control-plane and analytics functions from unaffected services. |
| [AWS S3 service disruption summary, 2017](https://aws.amazon.com/message/41926/) | Read the provider's original account of a historical regional service disruption. | Intermediate; public historical report. Its documented scope and corrective actions are specific to that event. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |
| [CNCF Slack community](https://slack.cncf.io/) | Find project and community discussion channels. | All levels; account and community-guideline acceptance required. Community support has no guaranteed service level. |

[Browse the other collections](README.md#resource-collections)

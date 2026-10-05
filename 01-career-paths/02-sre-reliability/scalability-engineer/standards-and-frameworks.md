# Scalability engineer: standards and frameworks

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

## Browse this page

- [Interface and measurement definitions](#interface-and-measurement-definitions)
- [Architecture and economic review](#architecture-and-economic-review)

## Interface and measurement definitions

Use these resources to make objective, traffic, protocol, and API assumptions explicit. They do not prescribe an application's partitioning or capacity model.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [TCP specification, RFC 9293](https://www.rfc-editor.org/rfc/rfc9293.html) | Review TCP transport semantics relevant to connection and retransmission investigations. | Advanced; public specification. The network path and application protocol add behavior beyond TCP. |
| [QUIC transport, RFC 9000](https://www.rfc-editor.org/rfc/rfc9000.html) | Review transport behavior relevant to modern HTTP and connection investigations. | Advanced; public specification. Use application and implementation references alongside the transport document. |
| [IP performance metrics framework, RFC 2330](https://www.rfc-editor.org/rfc/rfc2330.html) | Distinguish measurement definitions, samples, and network performance methodology. | Advanced; public foundational framework. Measurement location and sampling design affect interpretation. |
| [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) | Review machine-readable API contracts and compare documented requests, schemas, and responses. | Intermediate; public specification. The latest document may differ from the version supported by a chosen validator or client generator. |

## Architecture and economic review

Apply the provider and economic frameworks to the actual deployment, workload, and operating evidence. Record unresolved tradeoffs alongside the chosen design.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review AWS workload decisions and architectural trade-offs. | Intermediate to advanced; provider-specific framework, not an independent compliance audit. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Structure Azure workload reviews around documented quality concerns. | Intermediate to advanced; tailor review depth to business and workload needs. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Structure Google Cloud workload architecture reviews. | Intermediate to advanced; provider-specific assumptions require interpretation. |
| [FinOps Framework](https://www.finops.org/framework/) | Connect technology cost decisions with accountability and business value. | Intermediate; apply using actual operating and billing evidence. |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Intermediate; framework use is not itself evidence of technical control effectiveness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |

[Browse the other collections](README.md#resource-collections)

# Infrastructure reliability engineer: standards and frameworks

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

## Browse this page

- [Architecture, service measurement, and cost](#architecture-service-measurement-and-cost)
- [Security and infrastructure interfaces](#security-and-infrastructure-interfaces)

## Architecture, service measurement, and cost

Apply frameworks to the infrastructure's actual service boundaries and failure dependencies.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review AWS workload decisions and architectural trade-offs. | Intermediate to advanced; provider-specific framework, not an independent compliance audit. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Structure Azure workload reviews around documented quality concerns. | Intermediate to advanced; tailor review depth to business and workload needs. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Structure Google Cloud workload architecture reviews. | Intermediate to advanced; provider-specific assumptions require interpretation. |
| [FinOps Framework](https://www.finops.org/framework/) | Connect technology cost decisions with accountability and business value. | Intermediate; apply using actual operating and billing evidence. |
| [IP performance metrics framework, RFC 2330](https://www.rfc-editor.org/rfc/rfc2330.html) | Distinguish measurement definitions, samples, and network performance methodology. | Advanced; public foundational framework. Measurement location and sampling design affect interpretation. |

## Security and infrastructure interfaces

Review access, secure changes, container interfaces, transport, and control evidence. Specifications do not validate a recovery procedure.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Intermediate; framework use is not itself evidence of technical control effectiveness. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [Open Container Initiative specifications](https://opencontainers.org/) | Locate container image, runtime, and distribution specification work. | Advanced; verify the exact specification and version relevant to the component. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Advanced; certificate lifecycle and application configuration require additional guidance. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Review identity-layer protocol requirements and flows. | Advanced; distinguish authentication from resource authorization and verify implementation guidance. |
| [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html) | Review current protocol security recommendations for OAuth implementations. | Advanced; applies alongside the relevant OAuth specifications and implementation documentation. |

[Browse the other collections](README.md#resource-collections)

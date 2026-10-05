# Resilience engineer: standards and frameworks

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

## Browse this page

- [Service and state contracts](#service-and-state-contracts)
- [Review and risk frameworks](#review-and-risk-frameworks)

## Service and state contracts

Use shared objective definitions and protocol references to make service behavior, retry assumptions, and interfaces explicit.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [TCP specification, RFC 9293](https://www.rfc-editor.org/rfc/rfc9293.html) | Review TCP transport semantics relevant to connection and retransmission investigations. | Advanced; public specification. The network path and application protocol add behavior beyond TCP. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Advanced; certificate lifecycle and application configuration require additional guidance. |
| [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) | Review machine-readable API contracts and compare documented requests, schemas, and responses. | Intermediate; public specification. The latest document may differ from the version supported by a chosen validator or client generator. |
| [JSON Schema documentation](https://json-schema.org/learn/) | Find schema concepts and validation references for structured automation inputs and outputs. | Intermediate; public learning and reference collection. Choose a supported dialect; schema validation cannot prove operational intent or authorization. |

## Review and risk frameworks

Apply these frameworks to the actual provider, threat model, and operating boundaries. Community chaos principles guide experiments; they are not formal compliance evidence.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Intermediate; framework use is not itself evidence of technical control effectiveness. |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review AWS workload decisions and architectural trade-offs. | Intermediate to advanced; provider-specific framework, not an independent compliance audit. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Structure Azure workload reviews around documented quality concerns. | Intermediate to advanced; tailor review depth to business and workload needs. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Structure Google Cloud workload architecture reviews. | Intermediate to advanced; provider-specific assumptions require interpretation. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | Structure application-security verification requirements for platform-facing services. | Intermediate to advanced; choose a version and applicable verification scope. |

[Browse the other collections](README.md#resource-collections)

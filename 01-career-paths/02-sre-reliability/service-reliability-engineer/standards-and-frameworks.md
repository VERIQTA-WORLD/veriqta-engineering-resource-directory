# Service reliability engineer: standards and frameworks

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

## Browse this page

- [Service, API, and transport contracts](#service-api-and-transport-contracts)
- [Security and delivery review](#security-and-delivery-review)

## Service, API, and transport contracts

Distinguish objective schemas from normative protocol and interface definitions. Check applicability and implementation behavior for the deployed service.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Advanced; certificate lifecycle and application configuration require additional guidance. |
| [TCP specification, RFC 9293](https://www.rfc-editor.org/rfc/rfc9293.html) | Review TCP transport semantics relevant to connection and retransmission investigations. | Advanced; public specification. The network path and application protocol add behavior beyond TCP. |
| [QUIC transport, RFC 9000](https://www.rfc-editor.org/rfc/rfc9000.html) | Review transport behavior relevant to modern HTTP and connection investigations. | Advanced; public specification. Use application and implementation references alongside the transport document. |
| [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) | Review machine-readable API contracts and compare documented requests, schemas, and responses. | Intermediate; public specification. The latest document may differ from the version supported by a chosen validator or client generator. |
| [JSON Schema documentation](https://json-schema.org/learn/) | Find schema concepts and validation references for structured automation inputs and outputs. | Intermediate; public learning and reference collection. Choose a supported dialect; schema validation cannot prove operational intent or authorization. |

## Security and delivery review

Use the security and supply-chain guidance to review authority, dependencies, artifacts, and evidence. Listing a framework does not establish conformance.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Review identity-layer protocol requirements and flows. | Advanced; distinguish authentication from resource authorization and verify implementation guidance. |
| [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html) | Review current protocol security recommendations for OAuth implementations. | Advanced; applies alongside the relevant OAuth specifications and implementation documentation. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [SLSA specification](https://slsa.dev/spec/) | Review software supply-chain assurance and provenance requirements. | Advanced; consult the relevant stable version and track specification changes. |
| [SPDX specifications](https://spdx.dev/specifications/) | Review software bill of materials and associated information models. | Advanced; select a supported specification version and validate producer-consumer compatibility. |
| [CycloneDX specification](https://cyclonedx.org/specification/overview/) | Compare bill-of-materials formats and their documented scope. | Advanced; choose formats around downstream consumers and required evidence. |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | Structure application-security verification requirements for platform-facing services. | Intermediate to advanced; choose a version and applicable verification scope. |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Intermediate; framework use is not itself evidence of technical control effectiveness. |

[Browse the other collections](README.md#resource-collections)

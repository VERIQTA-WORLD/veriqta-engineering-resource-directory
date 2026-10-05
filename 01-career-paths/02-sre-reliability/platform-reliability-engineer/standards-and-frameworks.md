# Platform reliability engineer: standards and frameworks

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

## Browse this page

- [Delivery, artifact, and workload contracts](#delivery-artifact-and-workload-contracts)
- [Identity, service objectives, and governance](#identity-service-objectives-and-governance)

## Delivery, artifact, and workload contracts

Use these specifications and community principles to clarify artifacts, reconciliation, and evidence. Read project support and deployment restrictions separately.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenGitOps principles](https://opengitops.dev/) | Use shared principles to discuss declarative state, version history, pull, and reconciliation. | Intermediate; community principles. Evaluate whether the implementation meets them. |
| [SLSA specification](https://slsa.dev/spec/) | Review software supply-chain assurance and provenance requirements. | Advanced; consult the relevant stable version and track specification changes. |
| [Open Container Initiative specifications](https://opencontainers.org/) | Locate container image, runtime, and distribution specification work. | Advanced; verify the exact specification and version relevant to the component. |
| [SPDX specifications](https://spdx.dev/specifications/) | Review software bill of materials and associated information models. | Advanced; select a supported specification version and validate producer-consumer compatibility. |
| [CycloneDX specification](https://cyclonedx.org/specification/overview/) | Compare bill-of-materials formats and their documented scope. | Advanced; choose formats around downstream consumers and required evidence. |
| [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) | Review machine-readable API contracts and compare documented requests, schemas, and responses. | Intermediate; public specification. The latest document may differ from the version supported by a chosen validator or client generator. |
| [JSON Schema documentation](https://json-schema.org/learn/) | Find schema concepts and validation references for structured automation inputs and outputs. | Intermediate; public learning and reference collection. Choose a supported dialect; schema validation cannot prove operational intent or authorization. |

## Identity, service objectives, and governance

Distinguish protocol requirements from review frameworks. Apply them to platform authority, tenant boundaries, and operating evidence.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Review identity-layer protocol requirements and flows. | Advanced; distinguish authentication from resource authorization and verify implementation guidance. |
| [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html) | Review current protocol security recommendations for OAuth implementations. | Advanced; applies alongside the relevant OAuth specifications and implementation documentation. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Advanced; certificate lifecycle and application configuration require additional guidance. |
| [SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/) | Explore workload identity specifications and the SPIRE implementation ecosystem. | Advanced; workload identity complements rather than replaces application authorization. |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Intermediate; framework use is not itself evidence of technical control effectiveness. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [FinOps Framework](https://www.finops.org/framework/) | Connect technology cost decisions with accountability and business value. | Intermediate; apply using actual operating and billing evidence. |

[Browse the other collections](README.md#resource-collections)

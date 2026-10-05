# DevOps automation engineer: standards and frameworks

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Delivery and artifact trust

These references cover declarative delivery, provenance, secure development, and artifact inventory. Select the controls your workflow can actually evidence.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OpenGitOps principles](https://opengitops.dev/) | Use shared principles to discuss declarative state, version history, pull, and reconciliation. | Public reference. Intermediate; community principles. Evaluate whether the implementation meets them. |
| [SLSA specification](https://slsa.dev/spec/) | Review software supply-chain assurance and provenance requirements. | Public reference. Advanced; consult the relevant stable version and track specification changes. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Public reference. Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [SPDX specifications](https://spdx.dev/specifications/) | Review software bill of materials and associated information models. | Public reference. Advanced; select a supported specification version and validate producer-consumer compatibility. |
| [CycloneDX specification](https://cyclonedx.org/specification/overview/) | Compare bill-of-materials formats and their documented scope. | Public reference. Advanced; choose formats around downstream consumers and required evidence. |
| [Open Container Initiative specifications](https://opencontainers.org/) | Locate container image, runtime, and distribution specification work. | Public reference. Advanced; verify the exact specification and version relevant to the component. |

## API and identity contracts

Protocol specifications help review client behavior and federation. A standard does not configure the provider trust policy for you.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Public reference. Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Public reference. Advanced; certificate lifecycle and application configuration require additional guidance. |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Review identity-layer protocol requirements and flows. | Public reference. Advanced; distinguish authentication from resource authorization and verify implementation guidance. |
| [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html) | Review current protocol security recommendations for OAuth implementations. | Public reference. Advanced; applies alongside the relevant OAuth specifications and implementation documentation. |

## Security and economic review

Use security and cost frameworks to review exposure, operating responsibilities, and the total cost of the workflow.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | Structure application-security verification requirements for platform-facing services. | Public reference. Intermediate to advanced; choose a version and applicable verification scope. |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Public reference. Intermediate; framework use is not itself evidence of technical control effectiveness. |
| [FinOps Framework](https://www.finops.org/framework/) | Connect technology cost decisions with accountability and business value. | Public reference. Intermediate; apply using actual operating and billing evidence. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md)

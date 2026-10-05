# DevOps platform engineer: standards and frameworks

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Platform and architecture review aids

Community maturity and cloud workload frameworks have different scopes. Use them to structure evidence and decisions rather than claim certification.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [CNCF platform engineering maturity model](https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/) | Evaluate platform capabilities and improvement dimensions beyond the existence of a developer portal. | Intermediate; public community framework. A maturity model supports discussion; it does not certify a platform or prescribe one product stack. |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review AWS workload decisions and architectural trade-offs. | Public reference. Intermediate to advanced; provider-specific framework, not an independent compliance audit. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Structure Azure workload reviews around documented quality concerns. | Public reference. Intermediate to advanced; tailor review depth to business and workload needs. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Structure Google Cloud workload architecture reviews. | Public reference. Intermediate to advanced; provider-specific assumptions require interpretation. |
| [FinOps Framework](https://www.finops.org/framework/) | Connect technology cost decisions with accountability and business value. | Public reference. Intermediate; apply using actual operating and billing evidence. |

## Artifact, delivery, and development trust

Decide which service produces each record and which control verifies it. Inventory formats, provenance guidance, and declarative delivery principles serve different needs.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Open Container Initiative specifications](https://opencontainers.org/) | Locate container image, runtime, and distribution specification work. | Public reference. Advanced; verify the exact specification and version relevant to the component. |
| [SPDX specifications](https://spdx.dev/specifications/) | Review software bill of materials and associated information models. | Public reference. Advanced; select a supported specification version and validate producer-consumer compatibility. |
| [CycloneDX specification](https://cyclonedx.org/specification/overview/) | Compare bill-of-materials formats and their documented scope. | Public reference. Advanced; choose formats around downstream consumers and required evidence. |
| [SLSA specification](https://slsa.dev/spec/) | Review software supply-chain assurance and provenance requirements. | Public reference. Advanced; consult the relevant stable version and track specification changes. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Public reference. Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [OpenGitOps principles](https://opengitops.dev/) | Use shared principles to discuss declarative state, version history, pull, and reconciliation. | Public reference. Intermediate; community principles. Evaluate whether the implementation meets them. |

## Identity and secure service integration

Use identity and transport specifications with platform-specific implementation guidance. Review application security and organizational risk separately.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Review identity-layer protocol requirements and flows. | Public reference. Advanced; distinguish authentication from resource authorization and verify implementation guidance. |
| [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html) | Review current protocol security recommendations for OAuth implementations. | Public reference. Advanced; applies alongside the relevant OAuth specifications and implementation documentation. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Public reference. Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Public reference. Advanced; certificate lifecycle and application configuration require additional guidance. |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | Structure application-security verification requirements for platform-facing services. | Public reference. Intermediate to advanced; choose a version and applicable verification scope. |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Public reference. Intermediate; framework use is not itself evidence of technical control effectiveness. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md)

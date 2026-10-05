# Standards, protocols, and review frameworks

Specifications and frameworks relevant to delivery architecture, software supply chains, identity, security, and workload review. Separate normative protocol requirements from community guidance and vendor recommendations.

Select applicable versions and requirements before an assessment. Read supersession, errata, and status information at the original source; a linked specification is not automatically a legal or contractual obligation.

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

## Delivery and software supply-chain references

These resources have different authority and scope. A community principle, a security framework, and an industry specification are not interchangeable compliance requirements.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [OpenGitOps principles](https://opengitops.dev/) | Use shared principles to discuss declarative state, version history, pull, and reconciliation. | Intermediate; community principles. Evaluate whether the implementation meets them. |
| [SLSA specification](https://slsa.dev/spec/) | Review software supply-chain assurance and provenance requirements. | Advanced; consult the relevant stable version and track specification changes. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [SPDX specifications](https://spdx.dev/specifications/) | Review software bill of materials and associated information models. | Advanced; select a supported specification version and validate producer-consumer compatibility. |
| [CycloneDX specification](https://cyclonedx.org/specification/overview/) | Compare bill-of-materials formats and their documented scope. | Advanced; choose formats around downstream consumers and required evidence. |
| [Open Container Initiative specifications](https://opencontainers.org/) | Locate container image, runtime, and distribution specification work. | Advanced; verify the exact specification and version relevant to the component. |

## Identity, security review, and service communication

Use protocol specifications to settle interoperability questions. Use control frameworks to organize reviews; applying a checklist alone does not establish certification or compliance.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Review identity-layer protocol requirements and flows. | Advanced; distinguish authentication from resource authorization and verify implementation guidance. |
| [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html) | Review current protocol security recommendations for OAuth implementations. | Advanced; applies alongside the relevant OAuth specifications and implementation documentation. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Advanced; certificate lifecycle and application configuration require additional guidance. |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | Structure application-security verification requirements for platform-facing services. | Intermediate to advanced; choose a version and applicable verification scope. |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Intermediate; framework use is not itself evidence of technical control effectiveness. |

## Architecture and economic decision frameworks

Use these frameworks to structure discussion and evidence. They should guide questions, not predetermine a product choice.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review AWS workload decisions and architectural trade-offs. | Intermediate to advanced; provider-specific framework, not an independent compliance audit. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Structure Azure workload reviews around documented quality concerns. | Intermediate to advanced; tailor review depth to business and workload needs. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Structure Google Cloud workload architecture reviews. | Intermediate to advanced; provider-specific assumptions require interpretation. |
| [FinOps Framework](https://www.finops.org/framework/) | Connect technology cost decisions with accountability and business value. | Intermediate; apply using actual operating and billing evidence. |

---

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

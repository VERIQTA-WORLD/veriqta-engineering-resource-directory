# Database reliability engineer: standards and frameworks

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

## Browse this page

- [Service and recovery review frameworks](#service-and-recovery-review-frameworks)
- [Security, identity, and interface requirements](#security-identity-and-interface-requirements)

## Service and recovery review frameworks

Use these to document objectives and recovery assumptions; distinguish vendor frameworks from database protocol or transaction guarantees.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [AWS Well-Architected reliability pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | Review reliability questions for cloud workload foundations, change, and recovery. | Intermediate; public provider framework. Review actual service limits and workload evidence; framework use is not certification. |
| [Azure Well-Architected reliability guidance](https://learn.microsoft.com/en-us/azure/well-architected/reliability/) | Find provider guidance for failure analysis, redundancy, recovery, and reliability review. | Intermediate; public framework. Apply to the deployed services and their documented responsibility boundaries. |
| [Google Cloud reliability framework](https://cloud.google.com/architecture/framework/reliability) | Review workload reliability principles and provider-specific design considerations. | Intermediate; public framework. Architecture guidance does not guarantee that every managed service meets your objective. |
| [FinOps Framework](https://www.finops.org/framework/) | Connect technology cost decisions with accountability and business value. | Intermediate; apply using actual operating and billing evidence. |

## Security, identity, and interface requirements

Review access, transport, application verification, and secure change practices for the database service and its clients.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Intermediate; framework use is not itself evidence of technical control effectiveness. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | Structure application-security verification requirements for platform-facing services. | Intermediate to advanced; choose a version and applicable verification scope. |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Review identity-layer protocol requirements and flows. | Advanced; distinguish authentication from resource authorization and verify implementation guidance. |
| [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html) | Review current protocol security recommendations for OAuth implementations. | Advanced; applies alongside the relevant OAuth specifications and implementation documentation. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Advanced; certificate lifecycle and application configuration require additional guidance. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |

[Browse the other collections](README.md#resource-collections)

# Network reliability engineer: standards and frameworks

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Distinguish normative specifications, security guidance, community principles, and vendor review frameworks. Read the source document and select the version applicable to the implementation; listing a framework does not establish compliance.

## Browse this page

- [Network and service protocols](#network-and-service-protocols)
- [Measurement, trust, and risk review](#measurement-trust-and-risk-review)

## Network and service protocols

These specifications and foundational RFCs define different layers. Review updates and implementation guidance rather than assume the oldest document is the entire current protocol.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [TCP specification, RFC 9293](https://www.rfc-editor.org/rfc/rfc9293.html) | Review TCP transport semantics relevant to connection and retransmission investigations. | Advanced; public specification. The network path and application protocol add behavior beyond TCP. |
| [BGP-4, RFC 4271](https://www.rfc-editor.org/rfc/rfc4271.html) | Review BGP route exchange and decision behavior alongside implementation manuals. | Advanced; public RFC. Later RFCs extend and update the protocol; operational policy is environment-specific. |
| [DNS concepts, RFC 1034](https://www.rfc-editor.org/rfc/rfc1034.html) | Read foundational DNS concepts and name-resolution responsibilities. | Advanced; public foundational RFC. Later documents update parts of DNS behavior; consult relevant implementation and update references. |
| [DNSSEC introduction, RFC 4033](https://www.rfc-editor.org/rfc/rfc4033.html) | Understand DNS authentication concepts and boundaries when investigating validation failures. | Advanced; public RFC. DNSSEC authenticates DNS data; it is not transport encryption or general application authorization. |
| [QUIC transport, RFC 9000](https://www.rfc-editor.org/rfc/rfc9000.html) | Review transport behavior relevant to modern HTTP and connection investigations. | Advanced; public specification. Use application and implementation references alongside the transport document. |
| [IP performance metrics framework, RFC 2330](https://www.rfc-editor.org/rfc/rfc2330.html) | Distinguish measurement definitions, samples, and network performance methodology. | Advanced; public foundational framework. Measurement location and sampling design affect interpretation. |
| [HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. | Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy. |
| [TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/) | Review transport-security protocol requirements and behavior. | Advanced; certificate lifecycle and application configuration require additional guidance. |

## Measurement, trust, and risk review

Use service-objective schemas and security frameworks to organize evidence and authority. They do not prove forwarding or policy enforcement.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | Locate the framework and supporting security-risk-management resources. | Intermediate; framework use is not itself evidence of technical control effectiveness. |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | Structure application-security verification requirements for platform-facing services. | Intermediate to advanced; choose a version and applicable verification scope. |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Review identity-layer protocol requirements and flows. | Advanced; distinguish authentication from resource authorization and verify implementation guidance. |
| [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html) | Review current protocol security recommendations for OAuth implementations. | Advanced; applies alongside the relevant OAuth specifications and implementation documentation. |

[Browse the other collections](README.md#resource-collections)

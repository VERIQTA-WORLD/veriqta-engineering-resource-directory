# DevOps automation engineer: reference architectures and design guidance

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Retries and recoverable workflows

An automation design must account for duplicate requests and partial completion. Record which operations can be retried and which need reconciliation or human recovery.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Public reference. Advanced; operation semantics determine which retry behavior is safe. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Public reference. Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [The evolution of automation](https://sre.google/sre-book/automation-at-google/) | Study how automation changes operating practices and control boundaries. | Intermediate; public book chapter. Large-scale examples are design references, not a requirement to build an equivalent platform. |
| [Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/) | Compare patterns addressing distributed-system concerns and trade-offs. | Public reference. Intermediate; examples are provider-oriented, while many problem statements apply more broadly. |
| [The Twelve-Factor App](https://12factor.net/) | Review application configuration, deployment, and operability principles. | Public reference. Foundation to intermediate; useful design guidance, not a complete security or resilience architecture. |

## Cloud foundations and declarative control

Use provider foundations to locate identity, networking, state, and organizational boundaries. Select the provider you operate rather than combining incompatible blueprints.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Public reference. Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Public reference. Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Public reference. Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Public reference. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |
| [Terraform module development](https://developer.hashicorp.com/terraform/language/modules/develop) | Design reusable infrastructure modules with clear interfaces and documented responsibility boundaries. | Intermediate; public reference. Version modules and test upgrades against real consumer configurations. |

## Communicating automation boundaries

Document the trigger, execution identity, target systems, state store, evidence, and recovery owner. These references help review the resulting design.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Public reference. Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Public reference. Foundation onward; keep decisions connected to evidence and later changes. |
| [OpenGitOps principles](https://opengitops.dev/) | Use shared principles to discuss declarative state, version history, pull, and reconciliation. | Public reference. Intermediate; community principles. Evaluate whether the implementation meets them. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Public reference. Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Public reference. Intermediate; platform design must start with developer and operator needs. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

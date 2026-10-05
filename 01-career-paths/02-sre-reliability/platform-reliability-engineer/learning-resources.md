# Platform reliability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Platform engineering and service objectives](#platform-engineering-and-service-objectives)
- [Controllers, automation, and delivery](#controllers-automation-and-delivery)
- [Security, visibility, and operational economics](#security-visibility-and-operational-economics)
- [Foundation-level SRE training](#foundation-level-sre-training)

## Platform engineering and service objectives

Browse operating-model and reliability references alongside the platform-specific documentation. Set objectives around user work such as provision, build, deploy, and observe.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Intermediate; platform design must start with developer and operator needs. |
| [CNCF platform engineering maturity model](https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/) | Evaluate platform capabilities and improvement dimensions beyond the existence of a developer portal. | Intermediate; public community framework. A maturity model supports discussion; it does not certify a platform or prescribe one product stack. |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [SLO engineering case studies](https://sre.google/workbook/slo-engineering-case-studies/) | Compare service-objective decisions and measurement approaches in concrete cases. | Intermediate; public chapter. Keep the service boundary and user expectations explicit. |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |

## Controllers, automation, and delivery

Use project examples to understand reconciliation, test boundaries, and release evidence. Review external effects before applying an example.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes tutorials](https://kubernetes.io/docs/tutorials/) | Study official walkthroughs for workloads, services, configuration, and clusters. | Foundation to intermediate; use the version and environment expected by the tutorial. |
| [HashiCorp tutorials](https://developer.hashicorp.com/tutorials) | Find product-maintained tutorials for infrastructure, images, secrets, and related workflows. | Foundation to advanced; tutorial dependencies and cloud charges vary. |
| [Pulumi tutorials](https://www.pulumi.com/tutorials/) | Find infrastructure learning examples organized around supported tools and platforms. | Intermediate; review account, language, and cloud requirements before starting. |
| [Crossplane getting started](https://docs.crossplane.io/latest/get-started/) | Find project-maintained introductory control-plane examples and setup guidance. | Intermediate to advanced; public tutorial navigation. Providers can create external resources; confirm deletion behavior and clean those resources before removing the control plane. |
| [Backstage software templates](https://backstage.io/docs/features/software-templates/) | Design scaffolding interfaces for repeatable developer workflows. | Intermediate; public project documentation. Template actions execute with configured credentials; validate inputs and review privileged integrations. |
| [OpenGitOps principles](https://opengitops.dev/) | Use shared principles to discuss declarative state, version history, pull, and reconciliation. | Intermediate; community principles. Evaluate whether the implementation meets them. |
| [Release engineering](https://sre.google/sre-book/release-engineering/) | Study an original account of build, release, and deployment engineering. | Intermediate to advanced; Google-specific practices require adaptation. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |

## Security, visibility, and operational economics

Connect shared infrastructure choices to trust, evidence, and cost. Community collections are discovery sources rather than individually vetted implementations.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html) | Explore security and reliability together in system design and operations. | Advanced; openly readable. Examples require interpretation for your environment. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize cost accountability, allocation, forecasting, and optimization work. | Intermediate; a practice framework, not a tool or a guarantee of savings. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |
| [CNCF Cloud Native Landscape](https://landscape.cncf.io/) | Discover technologies across cloud-native categories and ecosystems. | Intermediate; directory inclusion is not endorsement or a recommendation to adopt. |
| [DORA capabilities](https://dora.dev/capabilities/) | Find research-informed delivery and organizational capability references. | Intermediate; assess evidence and local constraints before prioritizing changes. |

## Foundation-level SRE training

Use this direct beginner module to understand the operating practice and human responsibilities before turning to advanced implementation references. It is a topic option, not a required curriculum.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Microsoft Learn: introduction to SRE](https://learn.microsoft.com/en-us/training/modules/intro-to-site-reliability-engineering/) | Browse a beginner module explaining SRE context, principles, human responsibilities, and getting started. | Foundation; publicly readable training module with no stated prerequisites. Sign-in is required for profile-linked assessment results; it is introductory guidance, not a production implementation lab. |

[Browse the other collections](README.md#resource-collections)

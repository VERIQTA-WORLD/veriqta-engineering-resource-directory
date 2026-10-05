# DevOps platform engineer

This collection focuses on shared capabilities that help teams build, deliver, and operate software: pipeline services, developer interfaces, reusable infrastructure, deployment controls, identity, artifact services, telemetry, and platform recovery. It emphasizes the platform as an operated service with defined users, interfaces, ownership, and limits.

A platform may serve virtual machines, managed services, containers, or several environments. Select resources for the capabilities users need. A portal, Kubernetes cluster, or GitOps controller is one component, not proof that a complete platform exists.

[DevOps delivery careers](../README.md) · [All career categories](../../README.md)

## Browse the collection

| Collection | What you will find |
| --- | --- |
| [Toolkit](toolkit.md) | Tools grouped by implementation or operating task, with alternatives and selection notes. |
| [Official documentation](official-documentation.md) | Authoritative manuals, API references, and focused operating guides. |
| [Reference architectures](reference-architectures.md) | Documented designs, patterns, assumptions, and decision resources. |
| [Learning resources](learning-resources.md) | Books, tutorials, research, talks, and discovery collections by topic. |
| [Labs and projects](labs-and-projects.md) | Practice environments, examples, workshops, and implementation repositories. |
| [Production responsibilities](production-responsibilities.md) | Operating concerns connected to diagnostic, incident, and recovery resources. |
| [Standards and frameworks](standards-and-frameworks.md) | Specifications, security guidance, and review frameworks with scope distinctions. |
| [Related careers](related-careers.md) | Adjacent collections, their overlap, and their development status. |

## Useful entry points

Choose the reference that matches your immediate task. These links are starting points into the wider collections, not a required sequence.

| Resource | When to open it | Level and access |
| --- | --- | --- |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Intermediate; platform design must start with developer and operator needs. |
| [Backstage](https://backstage.io/docs/overview/what-is-backstage/) | Assess a developer portal, software catalog, templates, and integrations. | Intermediate; catalog quality and plugin maintenance need ownership. A portal alone is not a complete platform. |
| [GitHub reusable workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) | Define shared workflow interfaces, inputs, secrets, and calls between repositories. | Intermediate; public documentation. Review secret propagation, environment behavior, permissions, and version pinning. |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Advanced; namespaces alone do not provide every required isolation boundary. |
| [CNCF platform engineering maturity model](https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/) | Evaluate platform capabilities and improvement dimensions beyond the existence of a developer portal. | Intermediate; public community framework. A maturity model supports discussion; it does not certify a platform or prescribe one product stack. |
| [The evolving SRE engagement model](https://sre.google/workbook/engagement-model/) | Understand service engagement, collaboration, and operational responsibility boundaries. | Intermediate; public workbook chapter. Organizational labels and staffing models vary; explicitly agree ownership locally. |

## Coverage and practical use

developer interfaces, ownership and templates; reusable delivery services and runner isolation; provisioning APIs and reusable infrastructure; artifact and deployment services; tenancy, identity, policy and secrets; shared telemetry and platform reliability; versioning, recovery, adoption and cost.

Continuous integration and continuous delivery (CI/CD) describe connected delivery practices. Infrastructure as code (IaC) describes infrastructure managed through versioned configuration or code. GitOps resources address desired-state delivery and reconciliation. Use each approach only where its responsibilities and failure behavior are understood.

Official external destinations are used while the repository catalog is being established. Software, hosted-service, and cloud charges must be assessed separately from public access to a reference. Source review does not certify a deployment, a full course, or an entire book.

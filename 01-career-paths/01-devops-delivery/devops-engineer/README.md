# DevOps engineer

This collection covers implementing and operating software delivery workflows: source control, builds, infrastructure and configuration, deployment, observability, security, and recovery. It gives readers practical references for connecting those systems and investigating the failures that occur between them.

The role varies by organization. Use the task categories to find resources for your responsibilities, and agree which team owns applications, delivery services, cloud foundations, and production support. A broad collection is not a requirement to operate every tool listed.

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
| [Pro Git](https://git-scm.com/book/en/v2) | Strengthen understanding of Git behavior, collaboration, and repository workflows. | Foundation to intermediate; openly readable. Practice with disposable repositories. |
| [GitHub Actions](https://docs.github.com/en/actions) | Design repository workflows, reusable automation, environments, and runner arrangements. | Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Release engineering](https://sre.google/sre-book/release-engineering/) | Study an original account of build, release, and deployment engineering. | Intermediate to advanced; Google-specific practices require adaptation. |

## Coverage and practical use

version control, builds and artifact flow; CI/CD execution and runner operations; infrastructure and configuration changes; container packaging and deployment; observability and troubleshooting; identity and artifact trust; release safety, incidents, recovery and cost.

Continuous integration and continuous delivery (CI/CD) describe connected delivery practices. Infrastructure as code (IaC) describes infrastructure managed through versioned configuration or code. GitOps resources address desired-state delivery and reconciliation. Use each approach only where its responsibilities and failure behavior are understood.

Official external destinations are used while the repository catalog is being established. Software, hosted-service, and cloud charges must be assessed separately from public access to a reference. Source review does not certify a deployment, a full course, or an entire book.

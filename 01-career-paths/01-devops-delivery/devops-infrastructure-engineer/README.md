# DevOps infrastructure engineer

This collection focuses on the infrastructure that supports software delivery and production workloads: cloud foundations, machine images, host configuration, provisioning state, networking, identity, compute, storage, observability, and recovery. It connects infrastructure changes to the delivery workflows and operating evidence needed to manage them.

Separate infrastructure provisioning from application deployment and configuration ownership. Provider designs and operating procedures are environment-specific; use only those matching the actual cloud, distribution, and control-plane arrangement.

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
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Ansible inventory guide](https://docs.ansible.com/projects/ansible/latest/inventory_guide/intro_inventory.html) | Organize hosts, groups, variables, and inventory sources for controlled targeting. | Intermediate; public reference. Protect inventory data and test precedence before widening the target group. |
| [cloud-init documentation](https://cloudinit.readthedocs.io/en/latest/) | Compare first-boot provisioning, datasource handling, and machine initialization workflows. | Intermediate; public documentation. Instance metadata, credentials, and repeated initialization require careful review. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |
| [AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/) | Explore governed multi-account foundations and service operations. | Advanced; organizational decisions, identity, networking, and account policies remain essential. |

## Coverage and practical use

cloud foundations and identity boundaries; provisioning state, modules, drift and migration; image and host configuration lifecycle; network and container infrastructure; storage, backup and recovery; maintenance, upgrades and diagnostics; infrastructure security, telemetry, capacity and cost.

Continuous integration and continuous delivery (CI/CD) describe connected delivery practices. Infrastructure as code (IaC) describes infrastructure managed through versioned configuration or code. GitOps resources address desired-state delivery and reconciliation. Use each approach only where its responsibilities and failure behavior are understood.

Official external destinations are used while the repository catalog is being established. Software, hosted-service, and cloud charges must be assessed separately from public access to a reference. Source review does not certify a deployment, a full course, or an entire book.

# DevOps platform engineer: official documentation

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Platform interfaces and execution services

Review metadata models, template privileges, reusable workflow interfaces, and runner responsibility boundaries. Document supported versions and upgrade expectations.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Backstage software catalog](https://backstage.io/docs/features/software-catalog/) | Model service ownership and metadata discovery for a developer portal. | Intermediate; public documentation. Catalog metadata is not proof that a service meets production controls. |
| [Backstage software templates](https://backstage.io/docs/features/software-templates/) | Design scaffolding interfaces for repeatable developer workflows. | Intermediate; public project documentation. Template actions execute with configured credentials; validate inputs and review privileged integrations. |
| [GitHub reusable workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) | Define shared workflow interfaces, inputs, secrets, and calls between repositories. | Intermediate; public documentation. Review secret propagation, environment behavior, permissions, and version pinning. |
| [GitHub self-hosted runners](https://docs.github.com/en/actions/concepts/runners/self-hosted-runners) | Assess responsibility for runner machines and their execution environments. | Intermediate; public documentation. Untrusted jobs, persistent workspaces, network reachability, and patching require deliberate controls. |
| [GitHub workflow artifacts](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflow-artifacts) | Understand how outputs move between jobs and remain available after workflow execution. | Foundation onward; public documentation. Retention, access, and storage limits depend on service settings and account terms. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review workflow, dependency, runner, and credential security considerations. | Public reference. Intermediate; apply the guidance to the repository trust model and runner arrangement. |
| [GitLab Runner documentation](https://docs.gitlab.com/runner/) | Design and operate execution infrastructure for GitLab pipelines. | Public reference. Advanced; executor choice changes isolation and maintenance responsibilities. |
| [Jenkins security guidance](https://www.jenkins.io/doc/book/security/) | Review controller access, authorization, and security configuration. | Public reference. Advanced; plugin and agent boundaries also need review. |

## Infrastructure APIs and state-based interfaces

Keep resource ownership, module versioning, provider identities, and recovery explicit. A reconciler and a pipeline must not compete for the same resource.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Public reference. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |
| [Terraform module development](https://developer.hashicorp.com/terraform/language/modules/develop) | Design reusable infrastructure modules with clear interfaces and documented responsibility boundaries. | Intermediate; public reference. Version modules and test upgrades against real consumer configurations. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Public reference. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Terraform testing](https://developer.hashicorp.com/terraform/language/tests) | Review native test structures for modules and infrastructure workflows. | Public reference. Intermediate; some test arrangements create resources. Read execution and cleanup behavior first. |
| [Pulumi testing guide](https://www.pulumi.com/docs/iac/guides/testing/) | Compare unit, property, and integration approaches for infrastructure expressed as code. | Intermediate; public guide. Provider integration tests can create billable resources and require cleanup. |

## Tenancy and workload contracts

Use these when Kubernetes is part of the platform. Review isolation, permissions, resource behavior, traffic, persistent storage, and maintenance impact as one service contract.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Public reference. Advanced; namespaces alone do not provide every required isolation boundary. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Public reference. Intermediate; assess escalation paths, broad grants, and service-account use. |
| [Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/) | Structure cluster and workload security review. | Public reference. Intermediate; a checklist is a starting point, not proof of compliance. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Public reference. Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Public reference. Intermediate; a disruption budget is not a universal guarantee against outages. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Public reference. Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Kubernetes auditing](https://kubernetes.io/docs/tasks/debug/debug-cluster/audit/) | Plan evidence of API activity and its collection pipeline. | Advanced; public operational reference. Audit policy, backend performance, retention, and sensitive-data exposure require review. |

## Telemetry and provider foundations

Define the boundary between provider foundations and platform services. Check access, telemetry pipelines, and cloud review requirements in the actual environment.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Public reference. Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Public reference. Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Public reference. Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Public reference. Intermediate; validate actual permissions at the required resource scope. |
| [AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/) | Explore governed multi-account foundations and service operations. | Public reference. Advanced; organizational decisions, identity, networking, and account policies remain essential. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Public reference. Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Public reference. Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |

## Continue browsing

[Tool directory](toolkit.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

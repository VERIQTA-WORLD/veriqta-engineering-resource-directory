# DevOps consultant: official documentation

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Delivery and infrastructure controls

Use the primary references to check whether a proposed implementation actually supports the required controls in the client’s version and deployment model.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review workflow, dependency, runner, and credential security considerations. | Public reference. Intermediate; apply the guidance to the repository trust model and runner arrangement. |
| [GitHub self-hosted runners](https://docs.github.com/en/actions/concepts/runners/self-hosted-runners) | Assess responsibility for runner machines and their execution environments. | Intermediate; public documentation. Untrusted jobs, persistent workspaces, network reachability, and patching require deliberate controls. |
| [GitLab Runner documentation](https://docs.gitlab.com/runner/) | Design and operate execution infrastructure for GitLab pipelines. | Public reference. Advanced; executor choice changes isolation and maintenance responsibilities. |
| [Jenkins security guidance](https://www.jenkins.io/doc/book/security/) | Review controller access, authorization, and security configuration. | Public reference. Advanced; plugin and agent boundaries also need review. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Public reference. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform testing](https://developer.hashicorp.com/terraform/language/tests) | Review native test structures for modules and infrastructure workflows. | Public reference. Intermediate; some test arrangements create resources. Read execution and cleanup behavior first. |
| [Ansible Vault](https://docs.ansible.com/ansible/latest/vault_guide/index.html) | Review encrypted-data handling in configuration automation. | Public reference. Intermediate; encryption at rest does not prevent exposure after decryption. |

## Cloud review and foundations

Well-Architected material and foundation guides provide structured review prompts. Review the actual accounts, subscriptions, projects, identities, and network boundaries.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review workload decisions across operational, reliability, security, performance, cost, and sustainability concerns. | Public reference. Intermediate to advanced; AWS-specific guidance. Adapt recommendations to requirements. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Review Azure workload architecture and quality trade-offs. | Public reference. Intermediate to advanced; assess workload context rather than treating guidance as a universal checklist. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Review Google Cloud architecture guidance across its documented pillars. | Public reference. Intermediate to advanced; provider-specific capabilities and assumptions need review. |
| [AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/) | Explore governed multi-account foundations and service operations. | Public reference. Advanced; organizational decisions, identity, networking, and account policies remain essential. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Public reference. Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Public reference. Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |

## Platform security and operating constraints

Assess tenancy, permissions, resource isolation, traffic policy, and workload availability together. These references are useful when the client uses Kubernetes.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/) | Compare production setup considerations and operating models. | Public reference. Advanced; managed services retain workload and configuration responsibilities. |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Public reference. Advanced; namespaces alone do not provide every required isolation boundary. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Public reference. Intermediate; assess escalation paths, broad grants, and service-account use. |
| [Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/) | Structure cluster and workload security review. | Public reference. Intermediate; a checklist is a starting point, not proof of compliance. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Public reference. Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Public reference. Intermediate; a disruption budget is not a universal guarantee against outages. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Public reference. Intermediate; enforcement depends on the network implementation and its supported behavior. |

## Reliability, identity, telemetry, and economics

Identify who owns each control and where its evidence can be inspected. Keep architecture opinions separate from a provider’s documented behavior.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Google SRE books](https://sre.google/books/) | Locate original reliability, operational, and secure-system engineering references. | Public reference. Intermediate to advanced; examples reflect their authors' environments and publication periods. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Public reference. Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Public reference. Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Public reference. Intermediate; validate actual permissions at the required resource scope. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Public reference. Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize cost accountability, allocation, forecasting, and optimization work. | Public reference. Intermediate; a practice framework, not a tool or a guarantee of savings. |

## Continue browsing

[Tool directory](toolkit.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

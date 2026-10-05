# Official documentation for DevOps architects

Focused official references for infrastructure, delivery, platform, identity, and reliability decisions. Use this page when you need to check behavior or a design assumption. The [toolkit](toolkit.md) provides the broader product-manual directory.

Documentation links may follow a current or stable version. Confirm the version of the component you operate before applying its instructions.

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

## Delivery systems and infrastructure controls

Use these focused references when defining delivery-system boundaries and change controls. Tool-level manuals are also linked throughout the [toolkit](toolkit.md).

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review workflow, dependency, runner, and credential security considerations. | Intermediate; apply the guidance to the repository trust model and runner arrangement. |
| [GitLab Runner documentation](https://docs.gitlab.com/runner/) | Design and operate execution infrastructure for GitLab pipelines. | Advanced; executor choice changes isolation and maintenance responsibilities. |
| [Jenkins security guidance](https://www.jenkins.io/doc/book/security/) | Review controller access, authorization, and security configuration. | Advanced; plugin and agent boundaries also need review. |
| [Terraform state](https://developer.hashicorp.com/terraform/language/state) | Understand infrastructure mappings and state behavior before designing shared automation. | Intermediate; state may contain sensitive data. Protect storage and recovery procedures. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform testing](https://developer.hashicorp.com/terraform/language/tests) | Review native test structures for modules and infrastructure workflows. | Intermediate; some test arrangements create resources. Read execution and cleanup behavior first. |
| [Ansible Vault](https://docs.ansible.com/ansible/latest/vault_guide/index.html) | Review encrypted-data handling in configuration automation. | Intermediate; encryption at rest does not prevent exposure after decryption. |

## Kubernetes tenancy, workloads, and security

Use version-appropriate documentation. Cluster behavior depends on configuration, providers, controllers, and workload design.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/) | Compare production setup considerations and operating models. | Advanced; managed services retain workload and configuration responsibilities. |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Advanced; namespaces alone do not provide every required isolation boundary. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Intermediate; assess escalation paths, broad grants, and service-account use. |
| [Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/) | Structure cluster and workload security review. | Intermediate; a checklist is a starting point, not proof of compliance. |
| [Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) | Review health-check semantics and configuration. | Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Intermediate; a disruption budget is not a universal guarantee against outages. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Intermediate; enforcement depends on the network implementation and its supported behavior. |

## Cloud architecture and landing zones

Use provider guidance for the environment you actually operate. A landing zone provides foundations; it does not remove workload-level design obligations.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review workload decisions across operational, reliability, security, performance, cost, and sustainability concerns. | Intermediate to advanced; AWS-specific guidance. Adapt recommendations to requirements. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Review Azure workload architecture and quality trade-offs. | Intermediate to advanced; assess workload context rather than treating guidance as a universal checklist. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Review Google Cloud architecture guidance across its documented pillars. | Intermediate to advanced; provider-specific capabilities and assumptions need review. |
| [AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/) | Explore governed multi-account foundations and service operations. | Advanced; organizational decisions, identity, networking, and account policies remain essential. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |

## Reliability, identity, telemetry, and cost

Pair architecture-level guidance with the exact product documentation relevant to the chosen stack.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Google SRE books](https://sre.google/books/) | Locate original reliability, operational, and secure-system engineering references. | Intermediate to advanced; examples reflect their authors' environments and publication periods. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Intermediate; validate actual permissions at the required resource scope. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize cost accountability, allocation, forecasting, and optimization work. | Intermediate; a practice framework, not a tool or a guarantee of savings. |

---

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

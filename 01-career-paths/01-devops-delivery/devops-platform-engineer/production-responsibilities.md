# DevOps platform engineer: production responsibilities and operational resources

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Operate stable platform interfaces

Document supported workflows, versions, owners, and failure evidence. Changes to shared templates and modules can affect many teams even if the platform service itself remains available.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Backstage software templates](https://backstage.io/docs/features/software-templates/) | Design scaffolding interfaces for repeatable developer workflows. | Intermediate; public project documentation. Template actions execute with configured credentials; validate inputs and review privileged integrations. |
| [Backstage software catalog](https://backstage.io/docs/features/software-catalog/) | Model service ownership and metadata discovery for a developer portal. | Intermediate; public documentation. Catalog metadata is not proof that a service meets production controls. |
| [GitHub reusable workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) | Define shared workflow interfaces, inputs, secrets, and calls between repositories. | Intermediate; public documentation. Review secret propagation, environment behavior, permissions, and version pinning. |
| [Terraform module development](https://developer.hashicorp.com/terraform/language/modules/develop) | Design reusable infrastructure modules with clear interfaces and documented responsibility boundaries. | Intermediate; public reference. Version modules and test upgrades against real consumer configurations. |
| [The evolving SRE engagement model](https://sre.google/workbook/engagement-model/) | Understand service engagement, collaboration, and operational responsibility boundaries. | Intermediate; public workbook chapter. Organizational labels and staffing models vary; explicitly agree ownership locally. |

## Protect shared execution and artifact services

Review tenant boundaries, privileged jobs, runner isolation, artifact identity, retention, and restore paths. Test controller and service recovery as well as application deployments.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub self-hosted runners](https://docs.github.com/en/actions/concepts/runners/self-hosted-runners) | Assess responsibility for runner machines and their execution environments. | Intermediate; public documentation. Untrusted jobs, persistent workspaces, network reachability, and patching require deliberate controls. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review runner trust, workflow access, and delivery credential exposure. | Intermediate; public contributions and privileged jobs need distinct trust treatment. |
| [GitLab Runner documentation](https://docs.gitlab.com/runner/) | Design and operate execution infrastructure for GitLab pipelines. | Public reference. Advanced; executor choice changes isolation and maintenance responsibilities. |
| [Jenkins security guidance](https://www.jenkins.io/doc/book/security/) | Review controller access, authorization, and security configuration. | Public reference. Advanced; plugin and agent boundaries also need review. |
| [Jenkins backup and restore](https://www.jenkins.io/doc/book/system-administration/backing-up/) | Plan recovery of controller configuration and data rather than only rebuilding agents. | Intermediate; public operating guide. Protect backed-up secrets and exercise restore in an isolated environment. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Public reference. Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |

## Maintain tenancy and controlled changes

Check permissions, admission behavior, resource isolation, traffic policy, and maintenance effects. Define who owns failures that cross platform and application boundaries.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Public reference. Advanced; namespaces alone do not provide every required isolation boundary. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Public reference. Intermediate; assess escalation paths, broad grants, and service-account use. |
| [Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/) | Review controls for cluster and workload operation. | Public reference. Intermediate; assign each control an owner and evidence source. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Public reference. Intermediate; a disruption budget is not a universal guarantee against outages. |
| [Kubernetes node drain](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/) | Understand workload eviction during node maintenance. | Intermediate; public task guide. Draining changes availability; disruption budgets, local data, and unmanaged pods affect behavior. |
| [Kubernetes auditing](https://kubernetes.io/docs/tasks/debug/debug-cluster/audit/) | Plan evidence of API activity and its collection pipeline. | Advanced; public operational reference. Audit policy, backend performance, retention, and sensitive-data exposure require review. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Public reference. Advanced; official PDF. Application and schema compatibility must be tested in your own system. |

## Measure reliability and recover shared state

Give the platform meaningful user-facing objectives and actionable alerts. Restore tests should cover the dependent state and data that a rebuilt service still needs.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Public reference. Intermediate; useful measures depend on service behavior and user expectations. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Public reference. Advanced; validate alert behavior against real traffic and responder capacity. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Public reference. Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Public reference. Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Velero documentation](https://velero.io/docs/) | Review Kubernetes backup and restore mechanisms and provider requirements. | Public reference. Advanced; rehearse restore and verify application data consistency, not only object recreation. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Public reference. Advanced; use documentation matching the deployed database version and test restored data. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Public reference. Advanced; define recovery time and recovery point objectives and test the complete workload. |

## Control adoption burden and cost

Review platform usage, onboarding friction, recurring toil, and resource attribution. More platform features do not necessarily make delivery easier or cheaper.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [CNCF platform engineering maturity model](https://tag-app-delivery.cncf.io/whitepapers/platform-eng-maturity-model/) | Evaluate platform capabilities and improvement dimensions beyond the existence of a developer portal. | Intermediate; public community framework. A maturity model supports discussion; it does not certify a platform or prescribe one product stack. |
| [DORA software delivery metrics guide](https://dora.dev/guides/dora-metrics/) | Select delivery measurements and interpret them as improvement signals. | Foundation onward; public research-program guidance. Define measurement context; avoid using aggregate metrics to rank individual engineers. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Public reference. Intermediate; cost work requires billing and usage data, not estimates alone. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Public reference. Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Public reference. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Standards and frameworks](standards-and-frameworks.md)

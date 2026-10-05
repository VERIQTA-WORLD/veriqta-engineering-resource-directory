# DevOps infrastructure engineer: production responsibilities and operational resources

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Protect infrastructure ownership and change evidence

Record reviewed plans, protected state, controlled execution identities, and the observed outcome. Investigate drift and locks before changing state or retrying a run.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Public reference. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform import](https://developer.hashicorp.com/terraform/language/import) | Bring existing infrastructure into configuration while checking ownership and planned changes. | Intermediate; public reference. Import does not by itself reconstruct an accurate configuration or remove drift. |
| [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) | Review simulated changes and configuration differences before a deployment. | Intermediate; public reference. Module support varies, explicit task settings can allow changes, and diff output may expose secrets. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review runner trust, workflow access, and delivery credential exposure. | Intermediate; public contributions and privileged jobs need distinct trust treatment. |

## Maintain images, hosts, nodes, and capacity

Use maintenance procedures appropriate to the control plane. Review availability impact, resource pressure, bootstrap evidence, and supported upgrade paths before changing a fleet.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [cloud-init debugging guide](https://cloudinit.readthedocs.io/en/latest/howto/debugging.html) | Find status and log evidence when instance initialization fails. | Intermediate; public guide. Logs and rendered user data can contain sensitive information. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Ansible execution strategies](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_strategies.html) | Select batching, parallelism, and task ordering for a fleet change. | Intermediate; publicly readable. More parallel execution can increase blast radius and load on shared services. |
| [Kubernetes node drain](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/) | Understand workload eviction during node maintenance. | Intermediate; public task guide. Draining changes availability; disruption budgets, local data, and unmanaged pods affect behavior. |
| [Kubeadm cluster upgrades](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/) | Review documented version transitions and component order for kubeadm-managed clusters. | Advanced; public procedure. This is not the upgrade procedure for every managed Kubernetes service; back up and follow the supported version path. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Public reference. Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Linux control group v2 documentation](https://docs.kernel.org/admin-guide/cgroup-v2.html) | Understand hierarchical host resource control and interactions with service managers and container runtimes. | Advanced; public kernel reference tracking a development kernel at review time. Match the deployed kernel and verify cgroup mode and delegated permissions before experiments. |

## Operate access and traffic boundaries

Review least privilege, network isolation, secret delivery, and audit evidence. Avoid assuming a policy object proves enforcement on the actual traffic path.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Public reference. Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Public reference. Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Public reference. Intermediate; validate actual permissions at the required resource scope. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Public reference. Intermediate; assess escalation paths, broad grants, and service-account use. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Public reference. Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Kubernetes auditing](https://kubernetes.io/docs/tasks/debug/debug-cluster/audit/) | Plan evidence of API activity and its collection pipeline. | Advanced; public operational reference. Audit policy, backend performance, retention, and sensitive-data exposure require review. |
| [Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/) | Review controls for cluster and workload operation. | Public reference. Intermediate; assign each control an owner and evidence source. |

## Recover infrastructure and persistent data

Exercise recovery of state, control planes, databases, and workload volumes as appropriate. Validate data and service behavior after restoration, not only that a restore job finished.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Velero documentation](https://velero.io/docs/) | Review Kubernetes backup and restore mechanisms and provider requirements. | Public reference. Advanced; rehearse restore and verify application data consistency, not only object recreation. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Public reference. Advanced; use documentation matching the deployed database version and test restored data. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Public reference. Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Public reference. Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Public reference. Advanced; test identity, configuration, data, and traffic restoration together. |

## Review reliability and total operating cost

Relate infrastructure changes to service objectives, incidents, measured utilization, and recurring spend. Capacity and storage retention can dominate costs beyond the provisioned compute.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Public reference. Intermediate; useful measures depend on service behavior and user expectations. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Public reference. Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Public reference. Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Public reference. Intermediate; cost work requires billing and usage data, not estimates alone. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Public reference. Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Public reference. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |
| [GitLab database outage report, January 2017](https://about.gitlab.com/blog/2017/02/01/gitlab-dot-com-database-incident/) | Study an original recovery incident and the importance of tested backup procedures. | Public reference. Advanced; historical incident. Distinguish recorded facts from assumptions about present systems. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Standards and frameworks](standards-and-frameworks.md)

# DevOps infrastructure engineer: official documentation

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## State, modules, adoption, and replacement

Understand state and ownership before importing an unmanaged resource, replacing it, or editing lifecycle behavior. Protect plans and state as sensitive operational data.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform state](https://developer.hashicorp.com/terraform/language/state) | Understand infrastructure mappings and state behavior before designing shared automation. | Public reference. Intermediate; state may contain sensitive data. Protect storage and recovery procedures. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Public reference. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Terraform import](https://developer.hashicorp.com/terraform/language/import) | Bring existing infrastructure into configuration while checking ownership and planned changes. | Intermediate; public reference. Import does not by itself reconstruct an accurate configuration or remove drift. |
| [Terraform lifecycle rules](https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle) | Review replacement ordering, destruction protection, and ignored changes in resource definitions. | Intermediate; public language reference. Provider behavior and dependency relationships affect the actual change. |
| [Terraform module development](https://developer.hashicorp.com/terraform/language/modules/develop) | Design reusable infrastructure modules with clear interfaces and documented responsibility boundaries. | Intermediate; public reference. Version modules and test upgrades against real consumer configurations. |
| [Terraform testing](https://developer.hashicorp.com/terraform/language/tests) | Review native test structures for modules and infrastructure workflows. | Public reference. Intermediate; some test arrangements create resources. Read execution and cleanup behavior first. |
| [OpenTofu state documentation](https://opentofu.org/docs/language/state/) | Review state ownership and state-related workflows for OpenTofu-managed infrastructure. | Intermediate; publicly readable. State can hold sensitive attributes; assess the chosen backend's protection and recovery separately. |

## Machine initialization and fleet configuration

Use the correct inventory and execution boundaries. Diagnose bootstrap failures from the machine’s actual evidence rather than rerunning privileged initialization blindly.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [cloud-init documentation](https://cloudinit.readthedocs.io/en/latest/) | Compare first-boot provisioning, datasource handling, and machine initialization workflows. | Intermediate; public documentation. Instance metadata, credentials, and repeated initialization require careful review. |
| [cloud-init debugging guide](https://cloudinit.readthedocs.io/en/latest/howto/debugging.html) | Find status and log evidence when instance initialization fails. | Intermediate; public guide. Logs and rendered user data can contain sensitive information. |
| [systemd project documentation](https://systemd.io/) | Find project-maintained explanations, administrator references, interfaces, and navigation to the manual pages. | Intermediate; public discovery page. Review the selected manual separately and match features to the distribution's installed systemd version. |
| [Ansible inventory guide](https://docs.ansible.com/projects/ansible/latest/inventory_guide/intro_inventory.html) | Organize hosts, groups, variables, and inventory sources for controlled targeting. | Intermediate; public reference. Protect inventory data and test precedence before widening the target group. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) | Review simulated changes and configuration differences before a deployment. | Intermediate; public reference. Module support varies, explicit task settings can allow changes, and diff output may expose secrets. |
| [Ansible execution strategies](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_strategies.html) | Select batching, parallelism, and task ordering for a fleet change. | Intermediate; publicly readable. More parallel execution can increase blast radius and load on shared services. |
| [Linux control group v2 documentation](https://docs.kernel.org/admin-guide/cgroup-v2.html) | Understand hierarchical host resource control and interactions with service managers and container runtimes. | Advanced; public kernel reference tracking a development kernel at review time. Match the deployed kernel and verify cgroup mode and delegated permissions before experiments. |
| [Linux kernel networking documentation](https://docs.kernel.org/networking/) | Investigate kernel networking behavior beneath containers and host network tooling. | Advanced; public kernel reference tracking a development kernel at review time. Use documentation matching the deployed kernel and driver; some material addresses developers rather than operators. |

## Cloud foundations and identities

Use provider-specific references to organize accounts or projects, network boundaries, delegated administration, and workload permissions.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/) | Explore governed multi-account foundations and service operations. | Public reference. Advanced; organizational decisions, identity, networking, and account policies remain essential. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Public reference. Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Public reference. Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Public reference. Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Public reference. Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Public reference. Intermediate; validate actual permissions at the required resource scope. |

## Cluster infrastructure and persistent data

Review distribution-specific operating procedures alongside the upstream API model. Drain, upgrade, and restore actions can affect availability and data.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/) | Compare production setup considerations and operating models. | Public reference. Advanced; managed services retain workload and configuration responsibilities. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Public reference. Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Public reference. Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Kubernetes node drain](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/) | Understand workload eviction during node maintenance. | Intermediate; public task guide. Draining changes availability; disruption budgets, local data, and unmanaged pods affect behavior. |
| [Kubeadm cluster upgrades](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/) | Review documented version transitions and component order for kubeadm-managed clusters. | Advanced; public procedure. This is not the upgrade procedure for every managed Kubernetes service; back up and follow the supported version path. |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Public reference. Intermediate; assess escalation paths, broad grants, and service-account use. |

## Continue browsing

[Tool directory](toolkit.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

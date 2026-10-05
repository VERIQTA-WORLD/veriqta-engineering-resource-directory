# Infrastructure reliability engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [State and configuration reliability](#state-and-configuration-reliability)
- [Hosts and kernel resource control](#hosts-and-kernel-resource-control)
- [Cluster maintenance and persistent state](#cluster-maintenance-and-persistent-state)
- [Foundations, identity, and telemetry](#foundations-identity-and-telemetry)
- [Provider workload signals](#provider-workload-signals)

## State and configuration reliability

Read backend, concurrency, change, and error semantics before modifying state or rerunning an interrupted change.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform state](https://developer.hashicorp.com/terraform/language/state) | Understand infrastructure mappings and state behavior before designing shared automation. | Intermediate; state may contain sensitive data. Protect storage and recovery procedures. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Terraform import](https://developer.hashicorp.com/terraform/language/import) | Bring existing infrastructure into configuration while checking ownership and planned changes. | Intermediate; public reference. Import does not by itself reconstruct an accurate configuration or remove drift. |
| [Terraform lifecycle rules](https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle) | Review replacement ordering, destruction protection, and ignored changes in resource definitions. | Intermediate; public language reference. Provider behavior and dependency relationships affect the actual change. |
| [Ansible inventory guide](https://docs.ansible.com/projects/ansible/latest/inventory_guide/intro_inventory.html) | Organize hosts, groups, variables, and inventory sources for controlled targeting. | Intermediate; public reference. Protect inventory data and test precedence before widening the target group. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) | Review simulated changes and configuration differences before a deployment. | Intermediate; public reference. Module support varies, explicit task settings can allow changes, and diff output may expose secrets. |
| [Ansible execution strategies](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_strategies.html) | Select batching, parallelism, and task ordering for a fleet change. | Intermediate; publicly readable. More parallel execution can increase blast radius and load on shared services. |

## Hosts and kernel resource control

Match the deployed distribution and kernel. Development documentation is a design reference and may include features not present on the host.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [systemd project documentation](https://systemd.io/) | Find project-maintained explanations, administrator references, interfaces, and navigation to the manual pages. | Intermediate; public discovery page. Review the selected manual separately and match features to the distribution's installed systemd version. |
| [cloud-init documentation](https://cloudinit.readthedocs.io/en/latest/) | Compare first-boot provisioning, datasource handling, and machine initialization workflows. | Intermediate; public documentation. Instance metadata, credentials, and repeated initialization require careful review. |
| [cloud-init debugging guide](https://cloudinit.readthedocs.io/en/latest/howto/debugging.html) | Find status and log evidence when instance initialization fails. | Intermediate; public guide. Logs and rendered user data can contain sensitive information. |
| [Linux control group v2 documentation](https://docs.kernel.org/admin-guide/cgroup-v2.html) | Understand hierarchical host resource control and interactions with service managers and container runtimes. | Advanced; public kernel reference tracking a development kernel at review time. Match the deployed kernel and verify cgroup mode and delegated permissions before experiments. |
| [Linux kernel networking documentation](https://docs.kernel.org/networking/) | Investigate kernel networking behavior beneath containers and host network tooling. | Advanced; public kernel reference tracking a development kernel at review time. Use documentation matching the deployed kernel and driver; some material addresses developers rather than operators. |
| [Prometheus Node Exporter](https://github.com/prometheus/node_exporter) | Collect host metrics for resource pressure and infrastructure monitoring. | Intermediate; public project repository. Review enabled collectors, privileges, and host access boundaries. |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. |

## Cluster maintenance and persistent state

Use the actual distribution or managed-service procedure alongside upstream references. Drain, upgrade, and restore actions can affect availability and data.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/) | Compare production setup considerations and operating models. | Advanced; managed services retain workload and configuration responsibilities. |
| [Kubernetes node drain](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/) | Understand workload eviction during node maintenance. | Intermediate; public task guide. Draining changes availability; disruption budgets, local data, and unmanaged pods affect behavior. |
| [Kubeadm cluster upgrades](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/) | Review documented version transitions and component order for kubeadm-managed clusters. | Advanced; public procedure. This is not the upgrade procedure for every managed Kubernetes service; back up and follow the supported version path. |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Intermediate; a disruption budget is not a universal guarantee against outages. |

## Foundations, identity, and telemetry

Review cloud foundations and identities only for the providers used. Track telemetry collection and retention as operating dependencies.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/) | Explore governed multi-account foundations and service operations. | Advanced; organizational decisions, identity, networking, and account policies remain essential. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Intermediate; validate actual permissions at the required resource scope. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [Prometheus storage](https://prometheus.io/docs/prometheus/latest/storage/) | Review retention, local storage, and durability considerations for metrics infrastructure. | Advanced; public reference. Persistent storage is not a substitute for monitoring continuity or an exercised restore. |

## Provider workload signals

Use these documentation entry points to find the selected provider's metrics, logs, alerting, identity, and retention guidance. Check actual service impact independently of provider status.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon CloudWatch documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) | Find AWS monitoring, alarms, logs, service signals, and collection references for workload investigation. | Intermediate; public provider documentation. An AWS account and relevant permissions are needed to operate the service; collection, retention, and features have separate billing conditions. |
| [Azure Monitor overview](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview) | Review Azure's monitoring components and links for application and infrastructure observation. | Intermediate; public provider overview. Check the selected component's data collection, identity, retention, and charging model before deployment. |
| [Google Cloud Monitoring overview](https://cloud.google.com/monitoring/docs/monitoring-overview) | Find Google Cloud metric collection, dashboards, alerting, and monitoring integration references. | Intermediate; public provider documentation. Operating access requires appropriate project permissions; telemetry volume and selected services affect charges. |

[Browse the other collections](README.md#resource-collections)

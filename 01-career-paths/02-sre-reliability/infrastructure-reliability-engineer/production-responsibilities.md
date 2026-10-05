# Infrastructure reliability engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Diagnose infrastructure without losing service context](#diagnose-infrastructure-without-losing-service-context)
- [Control maintenance and configuration risk](#control-maintenance-and-configuration-risk)
- [Recover control planes and persistent data](#recover-control-planes-and-persistent-data)
- [Maintain headroom, identities, and operating evidence](#maintain-headroom-identities-and-operating-evidence)

## Diagnose infrastructure without losing service context

Gather resource, host, network, storage, and workload evidence. High CPU or a healthy host is not enough to explain the user outcome.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [The USE method](https://www.brendangregg.com/usemethod.html) | Organize resource analysis around utilization, saturation, and errors. | Intermediate; public author reference. High utilization alone does not establish the limiting resource. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Prometheus Node Exporter](https://github.com/prometheus/node_exporter) | Collect host metrics for resource pressure and infrastructure monitoring. | Intermediate; public project repository. Review enabled collectors, privileges, and host access boundaries. |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |

## Control maintenance and configuration risk

Review plans, state ownership, host targeting, node eviction, and supported version paths. Preserve the rollback and recovery evidence needed if maintenance fails.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) | Review simulated changes and configuration differences before a deployment. | Intermediate; public reference. Module support varies, explicit task settings can allow changes, and diff output may expose secrets. |
| [Kubernetes node drain](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/) | Understand workload eviction during node maintenance. | Intermediate; public task guide. Draining changes availability; disruption budgets, local data, and unmanaged pods affect behavior. |
| [Kubeadm cluster upgrades](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/) | Review documented version transitions and component order for kubeadm-managed clusters. | Advanced; public procedure. This is not the upgrade procedure for every managed Kubernetes service; back up and follow the supported version path. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Intermediate; a disruption budget is not a universal guarantee against outages. |

## Recover control planes and persistent data

Exercise restoration with the matching versions and dependencies. Verify quorum, data integrity, and useful workload behavior before declaring recovery.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |
| [etcd documentation](https://etcd.io/docs/) | Review distributed coordination, maintenance, recovery, and failure behavior. | Advanced; public versioned reference collection. Quorum, disk latency, and recovery state need explicit operating plans. |
| [Velero documentation](https://velero.io/docs/) | Review Kubernetes backup and restore mechanisms and provider requirements. | Advanced; rehearse restore and verify application data consistency, not only object recreation. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [GitLab database incident postmortem](https://about.gitlab.com/blog/gitlab-dot-com-database-incident/) | Study operational mistakes, recovery dependencies, and backup-validation lessons in an original report. | Intermediate; public historical incident account. Do not confuse configured backup procedures with demonstrated restore capability. |

## Maintain headroom, identities, and operating evidence

Keep expansion limits, privileged access, service indicators, incident roles, and cost consequences explicit.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Intermediate; combine with service-specific permissions and organization policies. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Intermediate; assess escalation paths, broad grants, and service-account use. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Intermediate; cost work requires billing and usage data, not estimates alone. |

[Browse the other collections](README.md#resource-collections)

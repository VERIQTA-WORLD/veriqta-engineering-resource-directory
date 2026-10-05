# Platform reliability engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [Cluster operation and change](#cluster-operation-and-change)
- [Delivery and provisioning state](#delivery-and-provisioning-state)
- [Catalog, tenancy, and trust](#catalog-tenancy-and-trust)
- [Telemetry and service evidence](#telemetry-and-service-evidence)

## Cluster operation and change

Use the documentation for the deployed release and review upgrade, disruption, storage, and control-plane recovery assumptions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/) | Compare production setup considerations and operating models. | Advanced; managed services retain workload and configuration responsibilities. |
| [Kubeadm cluster upgrades](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/) | Review documented version transitions and component order for kubeadm-managed clusters. | Advanced; public procedure. This is not the upgrade procedure for every managed Kubernetes service; back up and follow the supported version path. |
| [Kubernetes node drain](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/) | Understand workload eviction during node maintenance. | Intermediate; public task guide. Draining changes availability; disruption budgets, local data, and unmanaged pods affect behavior. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Intermediate; a disruption budget is not a universal guarantee against outages. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |
| [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) | Locate workload debugging references for deployment and runtime failures. | Intermediate; establish scope before applying changes. Read permissions and command effects. |
| [Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) | Review health-check semantics and configuration. | Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Intermediate; workload measurements and node capacity are needed for useful settings. |

## Delivery and provisioning state

Review runner isolation, credentials, controller ownership, and infrastructure state. A successful pipeline does not validate rollback or recovery of the platform itself.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub self-hosted runners](https://docs.github.com/en/actions/concepts/runners/self-hosted-runners) | Assess responsibility for runner machines and their execution environments. | Intermediate; public documentation. Untrusted jobs, persistent workspaces, network reachability, and patching require deliberate controls. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review workflow, dependency, runner, and credential security considerations. | Intermediate; apply the guidance to the repository trust model and runner arrangement. |
| [GitHub Actions OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect) | Evaluate identity federation between workflows and external providers. | Advanced; public conceptual guide. Trust policy must bind the intended repository and execution context, not merely the identity provider. |
| [GitLab Runner documentation](https://docs.gitlab.com/runner/) | Design and operate execution infrastructure for GitLab pipelines. | Advanced; executor choice changes isolation and maintenance responsibilities. |
| [Jenkins security guidance](https://www.jenkins.io/doc/book/security/) | Review controller access, authorization, and security configuration. | Advanced; plugin and agent boundaries also need review. |
| [Jenkins backup and restore](https://www.jenkins.io/doc/book/system-administration/backing-up/) | Plan recovery of controller configuration and data rather than only rebuilding agents. | Intermediate; public operating guide. Protect backed-up secrets and exercise restore in an isolated environment. |
| [Terraform state](https://developer.hashicorp.com/terraform/language/state) | Understand infrastructure mappings and state behavior before designing shared automation. | Intermediate; state may contain sensitive data. Protect storage and recovery procedures. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Crossplane getting started](https://docs.crossplane.io/latest/get-started/) | Find project-maintained introductory control-plane examples and setup guidance. | Intermediate to advanced; public tutorial navigation. Providers can create external resources; confirm deletion behavior and clean those resources before removing the control plane. |

## Catalog, tenancy, and trust

Connect catalog ownership and template effects to enforceable identity and tenant boundaries. Verify provider permissions and certificate lifecycle.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Backstage software catalog](https://backstage.io/docs/features/software-catalog/) | Model service ownership and metadata discovery for a developer portal. | Intermediate; public documentation. Catalog metadata is not proof that a service meets production controls. |
| [Backstage software templates](https://backstage.io/docs/features/software-templates/) | Design scaffolding interfaces for repeatable developer workflows. | Intermediate; public project documentation. Template actions execute with configured credentials; validate inputs and review privileged integrations. |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Advanced; namespaces alone do not provide every required isolation boundary. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Intermediate; assess escalation paths, broad grants, and service-account use. |
| [Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/) | Structure cluster and workload security review. | Intermediate; a checklist is a starting point, not proof of compliance. |
| [Ansible Vault](https://docs.ansible.com/ansible/latest/vault_guide/index.html) | Review encrypted-data handling in configuration automation. | Intermediate; encryption at rest does not prevent exposure after decryption. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Intermediate; validate actual permissions at the required resource scope. |
| [cert-manager documentation](https://cert-manager.io/docs/) | Evaluate certificate issuance and renewal automation for Kubernetes workloads. | Intermediate; public project documentation. Issuers, trust roots, DNS permissions, and renewal monitoring remain operational concerns. |

## Telemetry and service evidence

Review collection behavior, labels, retention, backend dependencies, and alert evaluation. Check the effect of a telemetry outage on platform diagnosis.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Prometheus recording rules](https://prometheus.io/docs/prometheus/latest/configuration/recording_rules/) | Plan reusable query results and rule evaluation for operational dashboards and alerts. | Intermediate; public reference. Rule evaluation load and failure visibility require operational review. |
| [Prometheus alerting rules](https://prometheus.io/docs/prometheus/latest/configuration/alerting_rules/) | Define actionable alert conditions and understand their evaluation behavior. | Intermediate; public reference. Alert expressions need routing, ownership, and diagnostic context. |
| [Prometheus storage](https://prometheus.io/docs/prometheus/latest/storage/) | Review retention, local storage, and durability considerations for metrics infrastructure. | Advanced; public reference. Persistent storage is not a substitute for monitoring continuity or an exercised restore. |
| [Prometheus instrumentation practices](https://prometheus.io/docs/practices/instrumentation/) | Select metrics and labels that answer operating questions without uncontrolled cardinality. | Intermediate; public guide. Instrumentation overhead and confidential label values need review. |
| [kube-prometheus](https://github.com/prometheus-operator/kube-prometheus) | Study manifests and dashboards for a Kubernetes monitoring stack. | Advanced; public implementation repository. Match supported Kubernetes versions and review resource use; remove the stack's resources when a practice cluster is retired. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |

[Browse the other collections](README.md#resource-collections)

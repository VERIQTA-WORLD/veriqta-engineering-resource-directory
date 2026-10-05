# DevOps infrastructure engineer: tool directory

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Declarative provisioning and state ownership

Compare language interfaces, providers, state backends, change previews, and recovery. Native cloud tools and cross-cloud tools have different operating dependencies.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Public reference. Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Public reference. Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Public reference. Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) | Review AWS resource provisioning, stack behavior, and change-management mechanisms. | Public reference. Intermediate; template support, stack boundaries, and rollback behavior must match the workload. |
| [Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/) | Evaluate declarative Azure infrastructure definitions and deployment workflows. | Public reference. Intermediate; provider-specific language and resource model. Review module, identity, and deployment-scope requirements. |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Public reference. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |

## Images, machine initialization, and configuration

Choose which layer owns packages, users, services, and bootstrap configuration. Avoid conflicting control between image builds, first boot, and ongoing configuration.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Packer](https://developer.hashicorp.com/packer/docs) | Build repeatable machine images and separate image creation from runtime configuration. | Public reference. Intermediate; image builders require credentials, compute, and artifact lifecycle management. |
| [cloud-init documentation](https://cloudinit.readthedocs.io/en/latest/) | Compare first-boot provisioning, datasource handling, and machine initialization workflows. | Intermediate; public documentation. Instance metadata, credentials, and repeated initialization require careful review. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Public reference. Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Vagrant documentation](https://developer.hashicorp.com/vagrant/docs) | Evaluate reproducible local virtual-machine environments for host and configuration experiments. | Foundation onward; public documentation. A supported virtualization provider and sufficient local resources are required. |
| [systemd project documentation](https://systemd.io/) | Find project-maintained explanations, administrator references, interfaces, and navigation to the manual pages. | Intermediate; public discovery page. Review the selected manual separately and match features to the distribution's installed systemd version. |

## Compute and container infrastructure

Review node, runtime, scheduling, packaging, and control-plane responsibilities separately. Include the cost of cluster upgrades and support.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [containerd](https://containerd.io/docs/) | Understand a container runtime layer and its operational interfaces. | Public reference. Advanced; primarily runtime and node architecture. It does not replace a delivery platform. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Public reference. Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Public reference. Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Public reference. Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |

## Network policy and traffic interfaces

Identify the required data path, policy enforcement point, and supported environment. These tools operate at different network layers and are not interchangeable.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Public reference. Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Calico](https://docs.tigera.io/calico/latest/about/) | Compare Kubernetes networking and network-policy approaches. | Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Public reference. Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Public reference. Intermediate; APIs require a compatible implementation. Check conformance and feature status. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Public reference. Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Public reference. Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. |

## Infrastructure credentials and guardrails

Check issuer trust, workload and operator access, rotation, and audit. Configuration encryption and centralized secret delivery solve different problems.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Public reference. Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [SOPS](https://github.com/getsops/sops) | Review encrypted configuration-file workflows with supported key services. | Public reference. Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak. |
| [External Secrets Operator](https://external-secrets.io/latest/) | Evaluate synchronization between external secret stores and Kubernetes. | Public reference. Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets. |
| [Keycloak](https://www.keycloak.org/documentation) | Evaluate identity and access-management capabilities for platform applications. | Public reference. Advanced; integration, federation, sessions, availability, and upgrades require specialist review. |
| [Open Policy Agent](https://www.openpolicyagent.org/docs/) | Evaluate general policy evaluation and integration patterns. | Public reference. Advanced; the integrating system must enforce the decision. Test policy and failure behavior. |
| [Kyverno](https://kyverno.io/docs/) | Assess Kubernetes policy validation, mutation, and other documented policy capabilities. | Public reference. Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests. |
| [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/) | Review managed secret storage, access, rotation, and service integrations. | Public reference. Intermediate; review IAM, rotation support, availability dependencies, and usage charges. |
| [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/) | Review managed secrets, keys, certificates, and access guidance. | Public reference. Intermediate; choose the relevant object and access model and plan recovery and billing. |
| [Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs) | Review managed secret versions, access, and application integration. | Public reference. Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing. |

## Testing, evidence, recovery, and cost

Use isolated tests to review infrastructure interfaces and change effects. Combine operational evidence with restore exercises and actual usage.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Ansible Molecule](https://docs.ansible.com/projects/molecule/) | Evaluate scenarios for developing and testing Ansible collections, playbooks, and roles. | Intermediate; public documentation. Scenario drivers and targets determine infrastructure, privileges, and cleanup requirements. |
| [Ansible Lint](https://docs.ansible.com/projects/lint/) | Check playbooks and roles for documented quality and maintainability rules. | Intermediate; public documentation. Lint passes do not establish desired-state correctness or successful recovery. |
| [Trivy](https://trivy.dev/latest/docs/) | Evaluate vulnerability and configuration assessment within build and deployment workflows. | Public reference. Intermediate; findings need prioritization and exceptions. Scan success does not establish artifact safety. |
| [pytest](https://docs.pytest.org/en/stable/) | Test Python automation with fixtures, assertions, parametrization, and temporary environments. | Intermediate; public project documentation. Mocks cannot establish that a live provider behaves correctly. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Public reference. Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Public reference. Intermediate; plan label cardinality, retention, storage, and availability. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Public reference. Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Public reference. Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Public reference. Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Public reference. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Public reference. Intermediate; allocation assumptions, data quality, and shared costs need review. |

## Changes through delivery systems

Choose an execution service that protects infrastructure state and credentials, records approvals and results, and handles competing runs.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub Actions](https://docs.github.com/en/actions) | Design repository workflows, reusable automation, environments, and runner arrangements. | Public reference. Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions. |
| [GitLab CI/CD](https://docs.gitlab.com/ci/) | Compare pipeline configuration, runners, artifacts, and delivery integration within GitLab. | Public reference. Intermediate; distinguish hosted and self-managed responsibilities and feature tiers. |
| [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) | Assess pipeline-as-code and extensibility for an operated automation service. | Public reference. Intermediate; controller, agents, plugins, credentials, upgrades, and backups require ownership. |
| [Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/) | Review hosted and self-hosted pipeline execution within Azure DevOps. | Public reference. Intermediate; agent pools, task permissions, and product access require review. |
| [AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/) | Review AWS-oriented delivery pipeline orchestration and service integrations. | Public reference. Intermediate; execution permissions, regions, integration costs, and artifact storage affect design. |
| [Google Cloud Build](https://cloud.google.com/build/docs) | Evaluate Google Cloud build execution, configuration, and associated integrations. | Public reference. Intermediate; review worker options, service identities, billing, and network access. |

## Continue browsing

[Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

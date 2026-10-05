# Infrastructure reliability engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Host, runtime, and resource evidence](#host-runtime-and-resource-evidence)
- [Provisioning, initialization, and configuration](#provisioning-initialization-and-configuration)
- [Container infrastructure and network controls](#container-infrastructure-and-network-controls)
- [Monitoring, recovery, and economic controls](#monitoring-recovery-and-economic-controls)
- [Infrastructure credentials and enforcement](#infrastructure-credentials-and-enforcement)
- [Provider monitoring options](#provider-monitoring-options)
- [Delegated operational jobs](#delegated-operational-jobs)

## Host, runtime, and resource evidence

Use host metrics and profiles to identify the affected resource and service. Kernel, privilege, and sampling requirements vary.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus Node Exporter](https://github.com/prometheus/node_exporter) | Collect host metrics for resource pressure and infrastructure monitoring. | Intermediate; public project repository. Review enabled collectors, privileges, and host access boundaries. |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |
| [BCC tools and examples](https://github.com/iovisor/bcc) | Explore eBPF-based tracing utilities for investigating operating-system behavior. | Advanced; public project repository. Tool support depends on kernel and build requirements; review privileges and collection overhead. |
| [bpftrace source and documentation](https://github.com/bpftrace/bpftrace) | Read tracing-language references and project guidance for Linux investigations. | Advanced; public tracing-language repository. Check release-specific language support, kernel requirements, privileges, and collection overhead. |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. |
| [stress-ng](https://github.com/ColinIanKing/stress-ng) | Explore controlled resource stressors for testing host and workload behavior. | Advanced; public project repository. Stressors can destabilize a host; use disposable environments and stop all stress processes afterward. |
| [sysbench](https://github.com/akopytov/sysbench) | Compare system and database benchmarking workloads in a controllable test environment. | Intermediate; public project repository. Benchmarks can saturate resources or alter test data; isolate targets. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. The linked manual currently displays development version 4.7.4; match the installed release. |

## Provisioning, initialization, and configuration

Maintain clear ownership among image creation, first boot, provisioning state, and ongoing configuration. Recoverability includes the state and credentials needed to operate these systems.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Packer](https://developer.hashicorp.com/packer/docs) | Build repeatable machine images and separate image creation from runtime configuration. | Intermediate; image builders require credentials, compute, and artifact lifecycle management. |
| [cloud-init documentation](https://cloudinit.readthedocs.io/en/latest/) | Compare first-boot provisioning, datasource handling, and machine initialization workflows. | Intermediate; public documentation. Instance metadata, credentials, and repeated initialization require careful review. |
| [systemd project documentation](https://systemd.io/) | Find project-maintained explanations, administrator references, interfaces, and navigation to the manual pages. | Intermediate; public discovery page. Review the selected manual separately and match features to the distribution's installed systemd version. |
| [Vagrant documentation](https://developer.hashicorp.com/vagrant/docs) | Evaluate reproducible local virtual-machine environments for host and configuration experiments. | Foundation onward; public documentation. A supported virtualization provider and sufficient local resources are required. |
| [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) | Review AWS resource provisioning, stack behavior, and change-management mechanisms. | Intermediate; template support, stack boundaries, and rollback behavior must match the workload. |
| [Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/) | Evaluate declarative Azure infrastructure definitions and deployment workflows. | Intermediate; provider-specific language and resource model. Review module, identity, and deployment-scope requirements. |

## Container infrastructure and network controls

Review runtime, cluster, node, traffic, and policy responsibilities separately. A cluster control plane is infrastructure that needs its own recovery plan.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [containerd](https://containerd.io/docs/) | Understand a container runtime layer and its operational interfaces. | Advanced; primarily runtime and node architecture. It does not replace a delivery platform. |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Calico](https://docs.tigera.io/calico/latest/about/) | Compare Kubernetes networking and network-policy approaches. | Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Intermediate; APIs require a compatible implementation. Check conformance and feature status. |

## Monitoring, recovery, and economic controls

Correlate fleet evidence with useful workload capacity and recoverable data. Monitoring availability and retained storage also belong in the operating plan.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |

## Infrastructure credentials and enforcement

Check execution identities, secret recovery, policy enforcement points, and permissions required for maintenance.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [SOPS](https://github.com/getsops/sops) | Review encrypted configuration-file workflows with supported key services. | Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak. |
| [External Secrets Operator](https://external-secrets.io/latest/) | Evaluate synchronization between external secret stores and Kubernetes. | Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets. |
| [Open Policy Agent](https://www.openpolicyagent.org/docs/) | Evaluate general policy evaluation and integration patterns. | Advanced; the integrating system must enforce the decision. Test policy and failure behavior. |
| [Kyverno](https://kyverno.io/docs/) | Assess Kubernetes policy validation, mutation, and other documented policy capabilities. | Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests. |
| [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/) | Review managed secret storage, access, rotation, and service integrations. | Intermediate; review IAM, rotation support, availability dependencies, and usage charges. |
| [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/) | Review managed secrets, keys, certificates, and access guidance. | Intermediate; choose the relevant object and access model and plan recovery and billing. |
| [Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs) | Review managed secret versions, access, and application integration. | Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing. |

## Provider monitoring options

Compare provider-native collection and alerting with your service instrumentation. Choose the relevant provider; public documentation and service operation have different access and cost conditions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon CloudWatch documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) | Find AWS monitoring, alarms, logs, service signals, and collection references for workload investigation. | Intermediate; public provider documentation. An AWS account and relevant permissions are needed to operate the service; collection, retention, and features have separate billing conditions. |
| [Azure Monitor overview](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview) | Review Azure's monitoring components and links for application and infrastructure observation. | Intermediate; public provider overview. Check the selected component's data collection, identity, retention, and charging model before deployment. |
| [Google Cloud Monitoring overview](https://cloud.google.com/monitoring/docs/monitoring-overview) | Find Google Cloud metric collection, dashboards, alerting, and monitoring integration references. | Intermediate; public provider documentation. Operating access requires appropriate project permissions; telemetry volume and selected services affect charges. |

## Delegated operational jobs

Compare job execution with scripts and controllers around target scope, credential handling, permissions, repeatability, and execution records.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Rundeck user guide](https://docs.rundeck.com/docs/manual/) | Review projects, jobs, execution, and access control for repeatable operational workflows. | Intermediate; public product documentation. Distinguish community and commercial capabilities; delegated job execution needs credential and target boundaries. |

[Browse the other collections](README.md#resource-collections)

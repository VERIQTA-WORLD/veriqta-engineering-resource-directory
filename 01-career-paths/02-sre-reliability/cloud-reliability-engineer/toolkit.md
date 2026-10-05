# Cloud reliability engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Provider health, limits, and resilience services](#provider-health-limits-and-resilience-services)
- [Infrastructure changes and fleet capacity](#infrastructure-changes-and-fleet-capacity)
- [Cloud-native workload and deployment services](#cloud-native-workload-and-deployment-services)
- [Workload signals and synthetic probes](#workload-signals-and-synthetic-probes)
- [Identity, data, traffic, and economics](#identity-data-traffic-and-economics)
- [Provider monitoring options](#provider-monitoring-options)

## Provider health, limits, and resilience services

Use provider information alongside workload telemetry. A provider assessment or healthy status page does not prove the workload is serving its users.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Health documentation](https://docs.aws.amazon.com/health/) | Find provider-event visibility and account-specific health information guidance. | Intermediate; public documentation. Provider status is one signal; it does not replace your own service measurements. |
| [Azure Service Health documentation](https://learn.microsoft.com/en-us/azure/service-health/) | Review provider incident, maintenance, and advisory visibility for Azure workloads. | Foundation onward; public reference. Access to account-specific information requires appropriate subscription permissions. |
| [Google Cloud Service Health documentation](https://cloud.google.com/service-health/docs/overview) | Find provider health and incident visibility guidance for cloud operations. | Intermediate; public reference. Compare provider events with workload telemetry and dependency evidence. |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |
| [AWS Resilience Hub documentation](https://docs.aws.amazon.com/resilience-hub/) | Compare documented application-resilience assessment and operational recommendations. | Advanced; public reference. Service assessment is not proof of exercised workload recovery; AWS permissions and charges require review. |
| [AWS Fault Injection Service documentation](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html) | Review managed fault experiments, targets, actions, and operating controls. | Advanced; public documentation. AWS account permissions and charges apply; review stop conditions and each action's recovery behavior. |
| [Azure Chaos Studio Workspaces documentation (preview)](https://learn.microsoft.com/en-us/azure/chaos-studio/) | Evaluate Azure fault experiments and service-specific target requirements. | Intermediate to advanced; public documentation for a preview service. Check feature scope, supported targets, account requirements, and preview limitations before planning an experiment. |

## Infrastructure changes and fleet capacity

Compare provider-native and cross-provider workflows, preserving resource ownership and state. Expansion depends on quotas, capacity, permissions, and startup time.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) | Review AWS resource provisioning, stack behavior, and change-management mechanisms. | Intermediate; template support, stack boundaries, and rollback behavior must match the workload. |
| [Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/) | Evaluate declarative Azure infrastructure definitions and deployment workflows. | Intermediate; provider-specific language and resource model. Review module, identity, and deployment-scope requirements. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Packer](https://developer.hashicorp.com/packer/docs) | Build repeatable machine images and separate image creation from runtime configuration. | Intermediate; image builders require credentials, compute, and artifact lifecycle management. |
| [Amazon EC2 Auto Scaling documentation](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) | Review instance-group scaling, health, and fleet operating behavior. | Intermediate; public reference. Scaling policies need capacity, permissions, startup time, and cost review. |
| [Azure Virtual Machine Scale Sets documentation](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/) | Find fleet scaling, configuration, upgrade, and operations guidance. | Intermediate; public reference collection. Check orchestration mode and the deployed image and service versions. |
| [Google Cloud managed instance groups](https://cloud.google.com/compute/docs/instance-groups) | Review VM group management, health, and scaling guidance. | Intermediate; public reference. Regional capacity, quotas, startup time, and managed-group configuration affect outcomes. |

## Cloud-native workload and deployment services

Include orchestration only where the workload needs it. Packaging, desired-state reconciliation, and rollout analysis have separate failure paths.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | Compare application synchronization, repository integration, and Kubernetes deployment management. | Intermediate; define repository and cluster trust boundaries, controller availability, and recovery. |
| [Flux](https://fluxcd.io/flux/) | Evaluate controller-based GitOps reconciliation for Kubernetes sources and workloads. | Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |
| [Flagger](https://docs.flagger.app/) | Explore automated progressive delivery with traffic-management and metric integrations. | Advanced; verify supported providers and analysis behavior for the chosen environment. |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |

## Workload signals and synthetic probes

Measure service outcomes and dependencies from useful observation points. The monitoring pipeline also has failure and retention requirements.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Sloth](https://sloth.dev/) | Compare an SLO-to-Prometheus rule generator for service monitoring workflows. | Intermediate; public project documentation. Correct generated rules still require valid indicators and label boundaries. |
| [Pyrra](https://github.com/pyrra-dev/pyrra) | Evaluate SLO definition and visualization tooling around Prometheus-based measurements. | Intermediate; public project repository. Review deployment requirements and the service's actual measurement coverage. |

## Identity, data, traffic, and economics

Review shared failure dependencies in credentials, data stores, ingress, and cost attribution. Products here address different layers rather than interchangeable solutions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/) | Review managed secret storage, access, rotation, and service integrations. | Intermediate; review IAM, rotation support, availability dependencies, and usage charges. |
| [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/) | Review managed secrets, keys, certificates, and access guidance. | Intermediate; choose the relevant object and access model and plan recovery and billing. |
| [Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs) | Review managed secret versions, access, and application integration. | Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing. |
| [PostgreSQL documentation](https://www.postgresql.org/docs/current/) | Locate administration, SQL, replication, security, and operating references for PostgreSQL. | Foundation onward; public documentation. The current alias tracks a changing major version; use the manual for the installed server. |
| [Redis documentation](https://redis.io/docs/latest/) | Find command, deployment, persistence, replication, and operating references for Redis products. | Foundation onward; public documentation. Distinguish product editions and deployment models; review applicable terms separately. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Intermediate; APIs require a compatible implementation. Check conformance and feature status. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |

## Provider monitoring options

Compare provider-native collection and alerting with your service instrumentation. Choose the relevant provider; public documentation and service operation have different access and cost conditions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon CloudWatch documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) | Find AWS monitoring, alarms, logs, service signals, and collection references for workload investigation. | Intermediate; public provider documentation. An AWS account and relevant permissions are needed to operate the service; collection, retention, and features have separate billing conditions. |
| [Azure Monitor overview](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview) | Review Azure's monitoring components and links for application and infrastructure observation. | Intermediate; public provider overview. Check the selected component's data collection, identity, retention, and charging model before deployment. |
| [Google Cloud Monitoring overview](https://cloud.google.com/monitoring/docs/monitoring-overview) | Find Google Cloud metric collection, dashboards, alerting, and monitoring integration references. | Intermediate; public provider documentation. Operating access requires appropriate project permissions; telemetry volume and selected services affect charges. |

[Browse the other collections](README.md#resource-collections)

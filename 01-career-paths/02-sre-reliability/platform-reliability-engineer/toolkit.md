# Platform reliability engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Provisioning and reconciliation](#provisioning-and-reconciliation)
- [Delivery and artifact services](#delivery-and-artifact-services)
- [Platform interfaces and policy](#platform-interfaces-and-policy)
- [Runtime and traffic dependencies](#runtime-and-traffic-dependencies)
- [Platform observability and capacity](#platform-observability-and-capacity)
- [Incident coordination options](#incident-coordination-options)
- [Delegated operational jobs](#delegated-operational-jobs)

## Provisioning and reconciliation

Compare infrastructure ownership, state handling, controller behavior, and provider dependencies. Check what happens to already running services when reconciliation or an API is unavailable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |

## Delivery and artifact services

Treat runners, controllers, registries, and signing infrastructure as production dependencies. Evaluate queueing, availability, credentials, storage, and recovery independently of the applications they deliver.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub Actions](https://docs.github.com/en/actions) | Design repository workflows, reusable automation, environments, and runner arrangements. | Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions. |
| [GitLab CI/CD](https://docs.gitlab.com/ci/) | Compare pipeline configuration, runners, artifacts, and delivery integration within GitLab. | Intermediate; distinguish hosted and self-managed responsibilities and feature tiers. |
| [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) | Assess pipeline-as-code and extensibility for an operated automation service. | Intermediate; controller, agents, plugins, credentials, upgrades, and backups require ownership. |
| [Tekton Pipelines](https://tekton.dev/docs/pipelines/) | Evaluate Kubernetes-native pipeline building blocks for a delivery platform. | Advanced; assumes Kubernetes. Budget for controllers, execution isolation, storage, and supporting services. |
| [Argo Workflows](https://argo-workflows.readthedocs.io/en/latest/) | Model container-based workflows and dependency graphs on Kubernetes. | Advanced; workflow orchestration and deployment reconciliation are different responsibilities. Do not confuse it with Argo CD. |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | Compare application synchronization, repository integration, and Kubernetes deployment management. | Intermediate; define repository and cluster trust boundaries, controller availability, and recovery. |
| [Flux](https://fluxcd.io/flux/) | Evaluate controller-based GitOps reconciliation for Kubernetes sources and workloads. | Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |
| [Harbor](https://goharbor.io/docs/) | Assess an operated container registry and its project, security, and replication capabilities. | Intermediate; registry availability, storage, upgrades, and retention become platform responsibilities. |
| [JFrog Artifactory documentation](https://jfrog.com/help/r/jfrog-artifactory-documentation) | Compare artifact repository capabilities across package formats and deployment options. | Intermediate; commercial features and operating models vary. Check entitlement and storage requirements. |
| [Sigstore Cosign](https://docs.sigstore.dev/cosign/signing/overview/) | Design artifact signing and verification workflows. | Advanced; define trusted identities, verification policy, and failure handling. A signature does not prove software quality. |

## Platform interfaces and policy

Use service catalogs and templates to make the platform usable, while keeping identity, ownership, tenancy, and policy enforcement explicit. A catalog entry is not evidence that a service is healthy.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Backstage](https://backstage.io/docs/overview/what-is-backstage/) | Assess a developer portal, software catalog, templates, and integrations. | Intermediate; catalog quality and plugin maintenance need ownership. A portal alone is not a complete platform. |
| [Keycloak](https://www.keycloak.org/documentation) | Evaluate identity and access-management capabilities for platform applications. | Advanced; integration, federation, sessions, availability, and upgrades require specialist review. |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [External Secrets Operator](https://external-secrets.io/latest/) | Evaluate synchronization between external secret stores and Kubernetes. | Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets. |
| [SOPS](https://github.com/getsops/sops) | Review encrypted configuration-file workflows with supported key services. | Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak. |
| [SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/) | Explore workload identity specifications and the SPIRE implementation ecosystem. | Advanced; workload identity complements rather than replaces application authorization. |
| [Open Policy Agent](https://www.openpolicyagent.org/docs/) | Evaluate general policy evaluation and integration patterns. | Advanced; the integrating system must enforce the decision. Test policy and failure behavior. |
| [Kyverno](https://kyverno.io/docs/) | Assess Kubernetes policy validation, mutation, and other documented policy capabilities. | Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests. |
| [Trivy](https://trivy.dev/latest/docs/) | Evaluate vulnerability and configuration assessment within build and deployment workflows. | Intermediate; findings need prioritization and exceptions. Scan success does not establish artifact safety. |

## Runtime and traffic dependencies

Match networking, certificates, gateways, and backup tools to the platform design. Review controller and data-plane failure separately.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [containerd](https://containerd.io/docs/) | Understand a container runtime layer and its operational interfaces. | Advanced; primarily runtime and node architecture. It does not replace a delivery platform. |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Calico](https://docs.tigera.io/calico/latest/about/) | Compare Kubernetes networking and network-policy approaches. | Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Intermediate; APIs require a compatible implementation. Check conformance and feature status. |
| [cert-manager documentation](https://cert-manager.io/docs/) | Evaluate certificate issuance and renewal automation for Kubernetes workloads. | Intermediate; public project documentation. Issuers, trust roots, DNS permissions, and renewal monitoring remain operational concerns. |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |

## Platform observability and capacity

Monitor user journeys and shared backends as well as cluster components. Include telemetry storage, incident routing, capacity, and allocation in the operating model.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Prometheus Node Exporter](https://github.com/prometheus/node_exporter) | Collect host metrics for resource pressure and infrastructure monitoring. | Intermediate; public project repository. Review enabled collectors, privileges, and host access boundaries. |
| [kube-state-metrics](https://github.com/kubernetes/kube-state-metrics) | Observe Kubernetes object state alongside workload and node performance metrics. | Intermediate; public project repository. Object-state metrics do not replace application-level service indicators. |
| [Thanos documentation](https://thanos.io/tip/thanos/getting-started.md/) | Compare a distributed metrics architecture and its component responsibilities. | Advanced; public project guide. The tip documentation can describe development features; select a matching release. |
| [VictoriaMetrics documentation](https://docs.victoriametrics.com/) | Compare documented metrics ingestion, querying, deployment, and operation options. | Intermediate to advanced; public reference collection. Distinguish single-node, cluster, and commercial feature boundaries. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |

## Incident coordination options

Compare incident workflows, ownership, escalation, and integration requirements. These hosted tools support coordination; they do not replace service objectives, diagnosis, or an agreed response process.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PagerDuty incident documentation](https://support.pagerduty.com/main/docs/incidents) | Inspect incident states, ownership, response, and notification behavior in a hosted incident platform. | Intermediate; public vendor documentation. Using the platform requires an account and suitable service access; review schedules, integrations, escalation, and feature availability. |
| [incident.io help center](https://docs.incident.io/) | Compare a hosted platform's incident response, on-call, alerting, and workflow documentation. | Intermediate; public vendor help center. Platform use requires an account and appropriate access; select direct guides and check integration and product boundaries. |

## Delegated operational jobs

Compare job execution with scripts and controllers around target scope, credential handling, permissions, repeatability, and execution records.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Rundeck user guide](https://docs.rundeck.com/docs/manual/) | Review projects, jobs, execution, and access control for repeatable operational workflows. | Intermediate; public product documentation. Distinguish community and commercial capabilities; delegated job execution needs credential and target boundaries. |

[Browse the other collections](README.md#resource-collections)

# DevOps consultant: tool directory

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Source control and delivery systems to compare

Compare the existing estate before proposing a migration. Evaluate runner ownership, integrations, access, artifact flow, and operational effort alongside workflow features.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Git](https://git-scm.com/docs) | Inspect branching, history, merging, and the source-control model behind delivery workflows. | Public reference. Foundation onward; a version-control tool, not a hosted collaboration platform. |
| [GitHub Actions](https://docs.github.com/en/actions) | Design repository workflows, reusable automation, environments, and runner arrangements. | Public reference. Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions. |
| [GitLab CI/CD](https://docs.gitlab.com/ci/) | Compare pipeline configuration, runners, artifacts, and delivery integration within GitLab. | Public reference. Intermediate; distinguish hosted and self-managed responsibilities and feature tiers. |
| [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) | Assess pipeline-as-code and extensibility for an operated automation service. | Public reference. Intermediate; controller, agents, plugins, credentials, upgrades, and backups require ownership. |
| [Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/) | Review hosted and self-hosted pipeline execution within Azure DevOps. | Public reference. Intermediate; agent pools, task permissions, and product access require review. |
| [AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/) | Review AWS-oriented delivery pipeline orchestration and service integrations. | Public reference. Intermediate; execution permissions, regions, integration costs, and artifact storage affect design. |
| [Google Cloud Build](https://cloud.google.com/build/docs) | Evaluate Google Cloud build execution, configuration, and associated integrations. | Public reference. Intermediate; review worker options, service identities, billing, and network access. |
| [Tekton Pipelines](https://tekton.dev/docs/pipelines/) | Evaluate Kubernetes-native pipeline building blocks for a delivery platform. | Public reference. Advanced; assumes Kubernetes. Budget for controllers, execution isolation, storage, and supporting services. |

## Infrastructure and configuration options

Use trials to compare state, interfaces, credentials, drift, and handover requirements. Tool choice should follow the operating model and the team’s skills.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Public reference. Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Public reference. Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Public reference. Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Public reference. Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Packer](https://developer.hashicorp.com/packer/docs) | Build repeatable machine images and separate image creation from runtime configuration. | Public reference. Intermediate; image builders require credentials, compute, and artifact lifecycle management. |
| [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) | Review AWS resource provisioning, stack behavior, and change-management mechanisms. | Public reference. Intermediate; template support, stack boundaries, and rollback behavior must match the workload. |
| [Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/) | Evaluate declarative Azure infrastructure definitions and deployment workflows. | Public reference. Intermediate; provider-specific language and resource model. Review module, identity, and deployment-scope requirements. |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Public reference. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |

## Container and deployment operating models

Determine whether orchestration and GitOps address a real need. Include upgrades, recovery, and support ownership in the proposal.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Public reference. Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Public reference. Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Public reference. Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | Compare application synchronization, repository integration, and Kubernetes deployment management. | Public reference. Intermediate; define repository and cluster trust boundaries, controller availability, and recovery. |
| [Flux](https://fluxcd.io/flux/) | Evaluate controller-based GitOps reconciliation for Kubernetes sources and workloads. | Public reference. Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Public reference. Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |

## Platform discovery and design communication

Use service metadata and architecture records to make the current environment understandable. A portal does not establish clear ownership without maintained metadata.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Backstage](https://backstage.io/docs/overview/what-is-backstage/) | Assess a developer portal, software catalog, templates, and integrations. | Public reference. Intermediate; catalog quality and plugin maintenance need ownership. A portal alone is not a complete platform. |
| [Structurizr documentation](https://docs.structurizr.com/) | Explore architecture models and diagram workflows based on the C4 approach. | Public reference. Intermediate; distinguish modeling tools and available deployment or service options. |
| [Mermaid](https://mermaid.js.org/intro/) | Create text-based diagrams alongside engineering documentation. | Public reference. Foundation onward; renderer versions and supported diagram features differ between publishing platforms. |

## Diagnostic and measurement capabilities

Select tools that can answer assessment questions about failure, latency, traffic, and load. Obtain permission before collecting sensitive evidence or generating traffic.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Public reference. Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Public reference. Intermediate; plan label cardinality, retention, storage, and availability. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Public reference. Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Public reference. Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Public reference. Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Public reference. Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Public reference. Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Public reference. Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |

## Security and artifact controls

Assess where existing controls are enforced and where exceptions are recorded. More scanners do not automatically produce better risk decisions.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Trivy](https://trivy.dev/latest/docs/) | Evaluate vulnerability and configuration assessment within build and deployment workflows. | Public reference. Intermediate; findings need prioritization and exceptions. Scan success does not establish artifact safety. |
| [Syft](https://github.com/anchore/syft) | Generate software bill of materials (SBOM) data from supported artifacts. | Public reference. Intermediate; inventory coverage depends on input and catalogers. Check downstream format requirements. |
| [Grype](https://github.com/anchore/grype) | Evaluate vulnerability matching against images, filesystems, or supported SBOM inputs. | Public reference. Intermediate; database freshness and package matching affect results. Establish a triage process. |
| [Sigstore Cosign](https://docs.sigstore.dev/cosign/signing/overview/) | Design artifact signing and verification workflows. | Public reference. Advanced; define trusted identities, verification policy, and failure handling. A signature does not prove software quality. |
| [OpenSSF Scorecard](https://scorecard.dev/) | Assess selected security practices of open-source projects during dependency review. | Public reference. Intermediate; scores are signals for investigation, not a complete security verdict. |
| [Open Policy Agent](https://www.openpolicyagent.org/docs/) | Evaluate general policy evaluation and integration patterns. | Public reference. Advanced; the integrating system must enforce the decision. Test policy and failure behavior. |
| [Kyverno](https://kyverno.io/docs/) | Assess Kubernetes policy validation, mutation, and other documented policy capabilities. | Public reference. Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests. |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Public reference. Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [Keycloak](https://www.keycloak.org/documentation) | Evaluate identity and access-management capabilities for platform applications. | Public reference. Advanced; integration, federation, sessions, availability, and upgrades require specialist review. |

## Cost and recovery assessment

Compare expected spend and recovery capabilities with measured usage and exercised procedures. Cost estimates and backup existence are incomplete evidence by themselves.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Public reference. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Public reference. Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Public reference. Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |
| [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/) | Review managed secret storage, access, rotation, and service integrations. | Public reference. Intermediate; review IAM, rotation support, availability dependencies, and usage charges. |
| [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/) | Review managed secrets, keys, certificates, and access guidance. | Public reference. Intermediate; choose the relevant object and access model and plan recovery and billing. |
| [Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs) | Review managed secret versions, access, and application integration. | Public reference. Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing. |

## Continue browsing

[Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

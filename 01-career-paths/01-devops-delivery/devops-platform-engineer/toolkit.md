# DevOps platform engineer: tool directory

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Developer-facing interfaces and architecture records

Choose interfaces around discoverability, ownership, and useful workflows. Keep catalog metadata and template behavior maintainable as teams and services change.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Backstage](https://backstage.io/docs/overview/what-is-backstage/) | Assess a developer portal, software catalog, templates, and integrations. | Public reference. Intermediate; catalog quality and plugin maintenance need ownership. A portal alone is not a complete platform. |
| [Structurizr documentation](https://docs.structurizr.com/) | Explore architecture models and diagram workflows based on the C4 approach. | Public reference. Intermediate; distinguish modeling tools and available deployment or service options. |
| [Mermaid](https://mermaid.js.org/intro/) | Create text-based diagrams alongside engineering documentation. | Public reference. Foundation onward; renderer versions and supported diagram features differ between publishing platforms. |
| [Git](https://git-scm.com/docs) | Inspect branching, history, merging, and the source-control model behind delivery workflows. | Public reference. Foundation onward; a version-control tool, not a hosted collaboration platform. |

## Shared build and workflow execution

Evaluate tenant isolation, runner supply, artifacts, credentials, configuration interfaces, and upgrades. A Kubernetes-native engine brings its own cluster dependency.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub Actions](https://docs.github.com/en/actions) | Design repository workflows, reusable automation, environments, and runner arrangements. | Public reference. Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions. |
| [GitLab CI/CD](https://docs.gitlab.com/ci/) | Compare pipeline configuration, runners, artifacts, and delivery integration within GitLab. | Public reference. Intermediate; distinguish hosted and self-managed responsibilities and feature tiers. |
| [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) | Assess pipeline-as-code and extensibility for an operated automation service. | Public reference. Intermediate; controller, agents, plugins, credentials, upgrades, and backups require ownership. |
| [Tekton Pipelines](https://tekton.dev/docs/pipelines/) | Evaluate Kubernetes-native pipeline building blocks for a delivery platform. | Public reference. Advanced; assumes Kubernetes. Budget for controllers, execution isolation, storage, and supporting services. |
| [Argo Workflows](https://argo-workflows.readthedocs.io/en/latest/) | Model container-based workflows and dependency graphs on Kubernetes. | Public reference. Advanced; workflow orchestration and deployment reconciliation are different responsibilities. Do not confuse it with Argo CD. |
| [Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/) | Review hosted and self-hosted pipeline execution within Azure DevOps. | Public reference. Intermediate; agent pools, task permissions, and product access require review. |
| [AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/) | Review AWS-oriented delivery pipeline orchestration and service integrations. | Public reference. Intermediate; execution permissions, regions, integration costs, and artifact storage affect design. |
| [Google Cloud Build](https://cloud.google.com/build/docs) | Evaluate Google Cloud build execution, configuration, and associated integrations. | Public reference. Intermediate; review worker options, service identities, billing, and network access. |
| [Bazel](https://bazel.build/about/intro) | Review a build system's dependency model, rules, caching, and execution guidance. | Public reference. Advanced; adoption depends on language rules and integration effort. Caching alone does not establish reproducibility. |
| [Testcontainers](https://testcontainers.com/guides/) | Find guides for container-backed integration test dependencies. | Public reference. Intermediate; runtime and language-library requirements vary. Tests still need meaningful assertions. |

## Reusable infrastructure and configuration

Design stable interfaces and ownership for provisioned resources. Compare state-based workflows with reconciled APIs before introducing another control plane.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Public reference. Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Public reference. Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Public reference. Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Public reference. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Public reference. Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Packer](https://developer.hashicorp.com/packer/docs) | Build repeatable machine images and separate image creation from runtime configuration. | Public reference. Intermediate; image builders require credentials, compute, and artifact lifecycle management. |
| [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) | Review AWS resource provisioning, stack behavior, and change-management mechanisms. | Public reference. Intermediate; template support, stack boundaries, and rollback behavior must match the workload. |
| [Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/) | Evaluate declarative Azure infrastructure definitions and deployment workflows. | Public reference. Intermediate; provider-specific language and resource model. Review module, identity, and deployment-scope requirements. |

## Workload packaging and deployment services

Define which service owns application desired state, promotion, rollout analysis, and recovery. Packaging conventions should be versioned like other platform interfaces.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Public reference. Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Public reference. Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Public reference. Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | Compare application synchronization, repository integration, and Kubernetes deployment management. | Public reference. Intermediate; define repository and cluster trust boundaries, controller availability, and recovery. |
| [Flux](https://fluxcd.io/flux/) | Evaluate controller-based GitOps reconciliation for Kubernetes sources and workloads. | Public reference. Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Public reference. Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |
| [Flagger](https://docs.flagger.app/) | Explore automated progressive delivery with traffic-management and metric integrations. | Public reference. Advanced; verify supported providers and analysis behavior for the chosen environment. |

## Artifact supply and platform trust

Treat registry operation, inventory, vulnerability triage, signing, and provenance as separate services or controls. Establish retention and recovery responsibilities.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Harbor](https://goharbor.io/docs/) | Assess an operated container registry and its project, security, and replication capabilities. | Public reference. Intermediate; registry availability, storage, upgrades, and retention become platform responsibilities. |
| [JFrog Artifactory documentation](https://jfrog.com/help/r/jfrog-artifactory-documentation) | Compare artifact repository capabilities across package formats and deployment options. | Intermediate; commercial features and operating models vary. Check entitlement and storage requirements. |
| [Trivy](https://trivy.dev/latest/docs/) | Evaluate vulnerability and configuration assessment within build and deployment workflows. | Public reference. Intermediate; findings need prioritization and exceptions. Scan success does not establish artifact safety. |
| [Syft](https://github.com/anchore/syft) | Generate software bill of materials (SBOM) data from supported artifacts. | Public reference. Intermediate; inventory coverage depends on input and catalogers. Check downstream format requirements. |
| [Grype](https://github.com/anchore/grype) | Evaluate vulnerability matching against images, filesystems, or supported SBOM inputs. | Public reference. Intermediate; database freshness and package matching affect results. Establish a triage process. |
| [Sigstore Cosign](https://docs.sigstore.dev/cosign/signing/overview/) | Design artifact signing and verification workflows. | Public reference. Advanced; define trusted identities, verification policy, and failure handling. A signature does not prove software quality. |
| [OpenSSF Scorecard](https://scorecard.dev/) | Assess selected security practices of open-source projects during dependency review. | Public reference. Intermediate; scores are signals for investigation, not a complete security verdict. |
| [SonarQube Server documentation](https://docs.sonarsource.com/sonarqube-server/) | Review code-analysis integration and quality-control capabilities. | Public reference. Intermediate; features and licensing vary. Analysis findings do not replace security review or runtime tests. |

## Tenancy, identity, secrets, and policy

Check how users, workloads, and controllers authenticate and how policy is enforced. Secret synchronization introduces another component and data exposure boundary.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Keycloak](https://www.keycloak.org/documentation) | Evaluate identity and access-management capabilities for platform applications. | Public reference. Advanced; integration, federation, sessions, availability, and upgrades require specialist review. |
| [SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/) | Explore workload identity specifications and the SPIRE implementation ecosystem. | Public reference. Advanced; workload identity complements rather than replaces application authorization. |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Public reference. Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [SOPS](https://github.com/getsops/sops) | Review encrypted configuration-file workflows with supported key services. | Public reference. Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak. |
| [External Secrets Operator](https://external-secrets.io/latest/) | Evaluate synchronization between external secret stores and Kubernetes. | Public reference. Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets. |
| [Open Policy Agent](https://www.openpolicyagent.org/docs/) | Evaluate general policy evaluation and integration patterns. | Public reference. Advanced; the integrating system must enforce the decision. Test policy and failure behavior. |
| [Kyverno](https://kyverno.io/docs/) | Assess Kubernetes policy validation, mutation, and other documented policy capabilities. | Public reference. Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests. |
| [cert-manager documentation](https://cert-manager.io/docs/) | Evaluate certificate issuance and renewal automation for Kubernetes workloads. | Intermediate; public project documentation. Issuers, trust roots, DNS permissions, and renewal monitoring remain operational concerns. |
| [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/) | Review managed secret storage, access, rotation, and service integrations. | Public reference. Intermediate; review IAM, rotation support, availability dependencies, and usage charges. |
| [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/) | Review managed secrets, keys, certificates, and access guidance. | Public reference. Intermediate; choose the relevant object and access model and plan recovery and billing. |
| [Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs) | Review managed secret versions, access, and application integration. | Public reference. Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing. |

## Traffic and service connectivity

Match policy and routing responsibilities to the supported workloads. Compare gateways, proxies, networking, and service meshes by the problem they solve.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Public reference. Intermediate; APIs require a compatible implementation. Check conformance and feature status. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Public reference. Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Public reference. Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Calico](https://docs.tigera.io/calico/latest/about/) | Compare Kubernetes networking and network-policy approaches. | Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Public reference. Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |

## Shared telemetry, recovery, and economics

Operate the monitoring path as a service too. Track telemetry volume, tenant attribution, resource consumption, recovery, and alert ownership.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Public reference. Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Public reference. Intermediate; plan label cardinality, retention, storage, and availability. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Public reference. Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Public reference. Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Public reference. Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Public reference. Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Public reference. Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Public reference. Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Public reference. Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Public reference. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |

## Continue browsing

[Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

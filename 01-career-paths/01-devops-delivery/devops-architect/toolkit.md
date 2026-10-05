# DevOps architect toolkit

A directory of tools for designing delivery and platform systems. Categories describe engineering needs; they are not a mandatory stack. Start with constraints and select the smallest set of components with clear ownership.

Each entry links to official documentation or a project-maintained source. Hosted products may have subscription or usage charges. Self-operated tools incur infrastructure and support costs even when their software is available without purchase.

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

## Source control and delivery pipelines

Choose a delivery system around runner isolation, permissions, artifact flow, integrations, and maintenance ownership. Continuous integration (CI) and continuous delivery (CD) are related capabilities, not guarantees of safe releases.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Git](https://git-scm.com/docs) | Inspect branching, history, merging, and the source-control model behind delivery workflows. | Foundation onward; a version-control tool, not a hosted collaboration platform. |
| [GitHub Actions](https://docs.github.com/en/actions) | Design repository workflows, reusable automation, environments, and runner arrangements. | Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions. |
| [GitLab CI/CD](https://docs.gitlab.com/ci/) | Compare pipeline configuration, runners, artifacts, and delivery integration within GitLab. | Intermediate; distinguish hosted and self-managed responsibilities and feature tiers. |
| [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) | Assess pipeline-as-code and extensibility for an operated automation service. | Intermediate; controller, agents, plugins, credentials, upgrades, and backups require ownership. |
| [Tekton Pipelines](https://tekton.dev/docs/pipelines/) | Evaluate Kubernetes-native pipeline building blocks for a delivery platform. | Advanced; assumes Kubernetes. Budget for controllers, execution isolation, storage, and supporting services. |
| [Argo Workflows](https://argo-workflows.readthedocs.io/en/latest/) | Model container-based workflows and dependency graphs on Kubernetes. | Advanced; workflow orchestration and deployment reconciliation are different responsibilities. Do not confuse it with Argo CD. |

## Infrastructure and configuration automation

Compare state management, drift behavior, credentials, approval boundaries, and recovery before choosing an infrastructure-as-code (IaC) approach.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Crossplane](https://docs.crossplane.io/latest/) | Explore API-driven infrastructure control and composition through Kubernetes. | Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery. |
| [Packer](https://developer.hashicorp.com/packer/docs) | Build repeatable machine images and separate image creation from runtime configuration. | Intermediate; image builders require credentials, compute, and artifact lifecycle management. |

## Containers, orchestration, and application packaging

Kubernetes is one operating model among several. Assess whether its capabilities justify the control-plane and support burden for the workload.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |
| [containerd](https://containerd.io/docs/) | Understand a container runtime layer and its operational interfaces. | Advanced; primarily runtime and node architecture. It does not replace a delivery platform. |

## GitOps and progressive delivery

Separate desired-state reconciliation from rollout control. Decide which component owns deployment state, promotion, analysis, and rollback.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | Compare application synchronization, repository integration, and Kubernetes deployment management. | Intermediate; define repository and cluster trust boundaries, controller availability, and recovery. |
| [Flux](https://fluxcd.io/flux/) | Evaluate controller-based GitOps reconciliation for Kubernetes sources and workloads. | Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |
| [Flagger](https://docs.flagger.app/) | Explore automated progressive delivery with traffic-management and metric integrations. | Advanced; verify supported providers and analysis behavior for the chosen environment. |

## Artifacts and software supply-chain tooling

Treat artifact storage, vulnerability assessment, signing, provenance, and enforcement as separate controls that must work together.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Harbor](https://goharbor.io/docs/) | Assess an operated container registry and its project, security, and replication capabilities. | Intermediate; registry availability, storage, upgrades, and retention become platform responsibilities. |
| [JFrog Artifactory documentation](https://jfrog.com/help/r/jfrog-artifactory-documentation) | Compare artifact repository capabilities across package formats and deployment options. | Intermediate; commercial features and operating models vary. Check entitlement and storage requirements. |
| [Trivy](https://trivy.dev/latest/docs/) | Evaluate vulnerability and configuration assessment within build and deployment workflows. | Intermediate; findings need prioritization and exceptions. Scan success does not establish artifact safety. |
| [Syft](https://github.com/anchore/syft) | Generate software bill of materials (SBOM) data from supported artifacts. | Intermediate; inventory coverage depends on input and catalogers. Check downstream format requirements. |
| [Grype](https://github.com/anchore/grype) | Evaluate vulnerability matching against images, filesystems, or supported SBOM inputs. | Intermediate; database freshness and package matching affect results. Establish a triage process. |
| [Sigstore Cosign](https://docs.sigstore.dev/cosign/signing/overview/) | Design artifact signing and verification workflows. | Advanced; define trusted identities, verification policy, and failure handling. A signature does not prove software quality. |
| [OpenSSF Scorecard](https://scorecard.dev/) | Assess selected security practices of open-source projects during dependency review. | Intermediate; scores are signals for investigation, not a complete security verdict. |

## Policy, identity, and secrets

Identify the trust boundary and enforcement point for each tool. Admission policy, identity federation, secret delivery, and audit evidence solve different problems.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Open Policy Agent](https://www.openpolicyagent.org/docs/) | Evaluate general policy evaluation and integration patterns. | Advanced; the integrating system must enforce the decision. Test policy and failure behavior. |
| [Kyverno](https://kyverno.io/docs/) | Assess Kubernetes policy validation, mutation, and other documented policy capabilities. | Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests. |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [External Secrets Operator](https://external-secrets.io/latest/) | Evaluate synchronization between external secret stores and Kubernetes. | Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets. |
| [SOPS](https://github.com/getsops/sops) | Review encrypted configuration-file workflows with supported key services. | Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak. |
| [Keycloak](https://www.keycloak.org/documentation) | Evaluate identity and access-management capabilities for platform applications. | Advanced; integration, federation, sessions, availability, and upgrades require specialist review. |
| [SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/) | Explore workload identity specifications and the SPIRE implementation ecosystem. | Advanced; workload identity complements rather than replaces application authorization. |

## Observability and diagnostics

Design useful telemetry and retention first. A larger tool stack does not automatically make failures easier to diagnose.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. |

## Networking and traffic management

Select ingress, gateway, proxy, network-policy, and service-to-service controls according to the actual traffic path and support model.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Calico](https://docs.tigera.io/calico/latest/about/) | Compare Kubernetes networking and network-policy approaches. | Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Intermediate; APIs require a compatible implementation. Check conformance and feature status. |

## Resilience, performance, and recovery

Choose experiments around hypotheses and measurable service behavior. Recovery tooling must be matched to storage and application consistency requirements.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |
| [Chaos Mesh](https://chaos-mesh.org/docs/) | Explore Kubernetes failure-injection experiments. | Advanced; use isolated environments and bounded experiments before considering production use. |
| [LitmusChaos](https://docs.litmuschaos.io/) | Compare chaos experimentation and workflow capabilities. | Advanced; assess permissions, compatibility, failure scope, and recovery controls. |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |

## Developer platforms, architecture records, and cost

These tools support platform discoverability and architectural decisions; they should follow a clear ownership and information model.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Backstage](https://backstage.io/docs/overview/what-is-backstage/) | Assess a developer portal, software catalog, templates, and integrations. | Intermediate; catalog quality and plugin maintenance need ownership. A portal alone is not a complete platform. |
| [Structurizr documentation](https://docs.structurizr.com/) | Explore architecture models and diagram workflows based on the C4 approach. | Intermediate; distinguish modeling tools and available deployment or service options. |
| [Mermaid](https://mermaid.js.org/intro/) | Create text-based diagrams alongside engineering documentation. | Foundation onward; renderer versions and supported diagram features differ between publishing platforms. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |

## Provider-native delivery and infrastructure options

These resources are useful when a provider integration or support model is a deliberate requirement. Compare portability and identity boundaries before committing to a provider-native workflow.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/) | Review hosted and self-hosted pipeline execution within Azure DevOps. | Intermediate; agent pools, task permissions, and product access require review. |
| [AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/) | Review AWS-oriented delivery pipeline orchestration and service integrations. | Intermediate; execution permissions, regions, integration costs, and artifact storage affect design. |
| [Google Cloud Build](https://cloud.google.com/build/docs) | Evaluate Google Cloud build execution, configuration, and associated integrations. | Intermediate; review worker options, service identities, billing, and network access. |
| [AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/) | Review AWS resource provisioning, stack behavior, and change-management mechanisms. | Intermediate; template support, stack boundaries, and rollback behavior must match the workload. |
| [Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/) | Evaluate declarative Azure infrastructure definitions and deployment workflows. | Intermediate; provider-specific language and resource model. Review module, identity, and deployment-scope requirements. |

## Build systems, test environments, and code analysis

Pipeline orchestration is only one part of verification. Build repeatability, test dependencies, and useful quality evidence also require explicit choices.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Bazel](https://bazel.build/about/intro) | Review a build system's dependency model, rules, caching, and execution guidance. | Advanced; adoption depends on language rules and integration effort. Caching alone does not establish reproducibility. |
| [Apache Maven](https://maven.apache.org/guides/) | Review build and dependency-management guidance for Maven-based projects. | Intermediate; assess plugin, repository, dependency, and credential governance. |
| [Testcontainers](https://testcontainers.com/guides/) | Find guides for container-backed integration test dependencies. | Intermediate; runtime and language-library requirements vary. Tests still need meaningful assertions. |
| [SonarQube Server documentation](https://docs.sonarsource.com/sonarqube-server/) | Review code-analysis integration and quality-control capabilities. | Intermediate; features and licensing vary. Analysis findings do not replace security review or runtime tests. |

## Provider-managed secret stores

Compare managed secret services with the secret-delivery and workload-identity model. A managed store does not automatically make application access appropriately scoped.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/) | Review managed secret storage, access, rotation, and service integrations. | Intermediate; review IAM, rotation support, availability dependencies, and usage charges. |
| [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/) | Review managed secrets, keys, certificates, and access guidance. | Intermediate; choose the relevant object and access model and plan recovery and billing. |
| [Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs) | Review managed secret versions, access, and application integration. | Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing. |

---

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

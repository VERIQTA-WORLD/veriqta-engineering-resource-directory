# DevOps architect: tools and technologies

[DevOps architect resource directory](README.md)

Use this directory when you are choosing components for a software delivery system. Compare tools by the responsibility they take on: source control, build execution, artifact trust, infrastructure change, deployment, runtime operation, and recovery. Continuous integration and continuous delivery (CI/CD) span several of these responsibilities; one pipeline engine does not supply the entire system.

The links lead primarily to official documentation or project-owned repositories. Those destinations are public reading; software licensing, hosted usage, enterprise features, and production support are separate decisions.

## Find resources by topic

- [Source control and pipeline execution](#source-control-and-pipeline-execution)
- [Build systems and automated verification](#build-systems-and-automated-verification)
- [Infrastructure definitions and machine configuration](#infrastructure-definitions-and-machine-configuration)
- [Containers and Kubernetes configuration](#containers-and-kubernetes-configuration)
- [Desired state and progressive delivery](#desired-state-and-progressive-delivery)
- [Artifacts and software supply-chain evidence](#artifacts-and-software-supply-chain-evidence)
- [Policy and deployment authorization](#policy-and-deployment-authorization)
- [Secrets and workload identity](#secrets-and-workload-identity)
- [Metrics logs traces and alert delivery](#metrics-logs-traces-and-alert-delivery)
- [Network policy routing and service communication](#network-policy-routing-and-service-communication)
- [Performance failure testing and recovery](#performance-failure-testing-and-recovery)
- [Developer interfaces architecture records and cost](#developer-interfaces-architecture-records-and-cost)

## Source control and pipeline execution

Start with where code lives, where builds execute, and who can change either. GitHub Actions and GitLab CI/CD fit their repository ecosystems; Jenkins introduces an operated controller and agents; Tekton and Argo Workflows introduce cluster dependencies.

- **[Git](https://git-scm.com/docs)** — Distributed version control for commits, branching, merging, and history inspection. Use its reference to understand the source model beneath any hosted workflow. Foundation onward; a version-control tool, not a hosted collaboration platform.

- **[GitHub Actions](https://docs.github.com/en/actions)** — Repository-based workflow execution with reusable jobs, hosted or self-hosted runners, and deployment integrations. Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions.

- **[GitLab CI/CD](https://docs.gitlab.com/ci/)** — Pipeline configuration, runner execution, artifacts, and delivery workflows integrated with GitLab repositories. Intermediate; distinguish hosted and self-managed responsibilities and feature tiers.

- **[Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/)** — A programmable automation service whose Pipeline DSL defines staged execution across agents. Intermediate; controller, agents, plugins, credentials, upgrades, and backups require ownership.

- **[Tekton Pipelines](https://tekton.dev/docs/pipelines/)** — Kubernetes-native pipeline components that represent tasks and pipeline runs as cluster resources. Advanced; assumes Kubernetes. Budget for controllers, execution isolation, storage, and supporting services.

- **[Argo Workflows](https://argo-workflows.readthedocs.io/en/latest/)** — A Kubernetes workflow engine for container-based steps and dependency graphs; useful for batch and orchestration workloads as well as automation. Advanced; workflow orchestration and deployment reconciliation are different responsibilities. Do not confuse it with Argo CD.

- **[Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/)** — Review hosted and self-hosted pipeline execution within Azure DevOps. Intermediate; agent pools, task permissions, and product access require review.

- **[AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/)** — Review AWS-oriented delivery pipeline orchestration and service integrations. Intermediate; execution permissions, regions, integration costs, and artifact storage affect design.

- **[Google Cloud Build](https://cloud.google.com/build/docs)** — Evaluate Google Cloud build execution, configuration, and associated integrations. Intermediate; review worker options, service identities, billing, and network access.

## Build systems and automated verification

Build orchestration and application build systems solve different problems. Select tests and quality gates that produce useful evidence, and account for their execution time, false positives, and privileged access.

- **[Bazel](https://bazel.build/about/intro)** — Review a build system's dependency model, rules, caching, and execution guidance. Advanced; adoption depends on language rules and integration effort. Caching alone does not establish reproducibility.

- **[Apache Maven](https://maven.apache.org/guides/)** — Review build and dependency-management guidance for Maven-based projects. Intermediate; assess plugin, repository, dependency, and credential governance.

- **[Testcontainers](https://testcontainers.com/guides/)** — Find guides for container-backed integration test dependencies. Intermediate; runtime and language-library requirements vary. Tests still need meaningful assertions.

- **[SonarQube Server documentation](https://docs.sonarsource.com/sonarqube-server/)** — Review code-analysis integration and quality-control capabilities. Intermediate; features and licensing vary. Analysis findings do not replace security review or runtime tests.

## Infrastructure definitions and machine configuration

Choose the state owner and change interface before selecting a language. Provisioning engines, configuration tools, image builders, and infrastructure control planes have different lifecycles.

- **[Terraform](https://developer.hashicorp.com/terraform/docs)** — Declarative infrastructure provisioning through providers, with plans and state connecting configuration to managed resources. Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review.

- **[OpenTofu](https://opentofu.org/docs/)** — A declarative infrastructure engine with provider configuration, planning, and state workflows. Compare its own documentation and compatibility requirements before a migration. Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability.

- **[Pulumi IaC](https://www.pulumi.com/docs/iac/)** — Infrastructure definitions using supported programming languages, with an engine that tracks deployments and resource state. Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies.

- **[AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/)** — Review AWS resource provisioning, stack behavior, and change-management mechanisms. Intermediate; template support, stack boundaries, and rollback behavior must match the workload.

- **[Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/)** — Evaluate declarative Azure infrastructure definitions and deployment workflows. Intermediate; provider-specific language and resource model. Review module, identity, and deployment-scope requirements.

- **[Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html)** — Agentless configuration and orchestration through inventories, modules, and playbooks. Intermediate; idempotency depends on modules and task design. Check collection and target compatibility.

- **[Packer](https://developer.hashicorp.com/packer/docs)** — Automated machine-image creation across supported builders; useful when you need reproducible base images rather than in-place host configuration. Intermediate; image builders require credentials, compute, and artifact lifecycle management.

- **[Crossplane](https://docs.crossplane.io/latest/)** — Kubernetes-based infrastructure control planes using providers and compositions to expose managed infrastructure APIs. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery.

## Containers and Kubernetes configuration

Separate image construction, container execution, orchestration, and application packaging. Kubernetes is one possible runtime, not a required answer for every workload.

- **[Docker documentation](https://docs.docker.com/)** — Container build and runtime documentation, including images, networking, storage, and developer workflows. Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms.

- **[containerd](https://containerd.io/docs/)** — A container runtime managing image transfer, storage, execution, and runtime lifecycle below an orchestrator. Advanced; primarily runtime and node architecture. It does not replace a delivery platform.

- **[Kubernetes](https://kubernetes.io/docs/)** — Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions.

- **[Helm](https://helm.sh/docs/)** — Kubernetes application packaging using charts, values, templates, and release operations. Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership.

- **[Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/)** — Customization of Kubernetes manifests through bases, overlays, patches, and transformations, without chart templating. Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling.

## Desired state and progressive delivery

GitOps is reconciliation of declared state; canary control is evaluation and progression of a release. Decide how manual interventions, drift, health checks, and emergency changes interact.

- **[Argo CD](https://argo-cd.readthedocs.io/en/stable/)** — Declarative Kubernetes application delivery that compares live resources with desired configuration and manages synchronization. Intermediate; define repository and cluster trust boundaries, controller availability, and recovery.

- **[Flux](https://fluxcd.io/flux/)** — Kubernetes reconciliation controllers for sources, configuration, Helm releases, and related GitOps workflows. Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery.

- **[Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/)** — Kubernetes rollout control for canary and blue-green strategies, including traffic management and analysis integration. Advanced; traffic routing and metrics integrations determine what a rollout can actually verify.

- **[Flagger](https://docs.flagger.app/)** — Automated progressive delivery for Kubernetes workloads using metrics and supported traffic integrations. Advanced; verify supported providers and analysis behavior for the chosen environment.

- **[OpenGitOps principles](https://opengitops.dev/)** — Use shared principles to discuss declarative state, version history, pull, and reconciliation. Intermediate; community principles. Evaluate whether the implementation meets them.

## Artifacts and software supply-chain evidence

You need to know what was built, where it came from, how it was verified, and who can promote it. A scan result, signature, or software bill of materials answers only part of that chain.

- **[Harbor](https://goharbor.io/docs/)** — A container-image and artifact registry with access controls, replication, and vulnerability-scanning integrations. Intermediate; registry availability, storage, upgrades, and retention become platform responsibilities.

- **[JFrog Artifactory documentation](https://jfrog.com/help/r/jfrog-artifactory-documentation)** — Compare artifact repository capabilities across package formats and deployment options. Intermediate; commercial features and operating models vary. Check entitlement and storage requirements.

- **[Trivy](https://trivy.dev/latest/docs/)** — Evaluate vulnerability and configuration assessment within build and deployment workflows. Intermediate; findings need prioritization and exceptions. Scan success does not establish artifact safety.

- **[Syft](https://github.com/anchore/syft)** — A CLI and library for generating software bills of materials from container images and filesystems. Intermediate; inventory coverage depends on input and catalogers. Check downstream format requirements.

- **[Grype](https://github.com/anchore/grype)** — A vulnerability scanner matching image, filesystem, or software-bill-of-materials packages to vulnerability information. Intermediate; database freshness and package matching affect results. Establish a triage process.

- **[Sigstore Cosign](https://docs.sigstore.dev/cosign/signing/overview/)** — Artifact signing and verification tooling in the Sigstore ecosystem; signatures need explicit identity and trust policy to be useful. Advanced; define trusted identities, verification policy, and failure handling. A signature does not prove software quality.

- **[OpenSSF Scorecard](https://scorecard.dev/)** — Assess selected security practices of open-source projects during dependency review. Intermediate; scores are signals for investigation, not a complete security verdict.

- **[SLSA specification](https://slsa.dev/spec/)** — Review software supply-chain assurance and provenance requirements. Advanced; consult the relevant stable version and track specification changes.

## Policy and deployment authorization

Compare a general policy evaluator with Kubernetes-native policy management. Establish who owns policies, how exceptions expire, and how policy changes are tested.

- **[Open Policy Agent](https://www.openpolicyagent.org/docs/)** — A policy engine that evaluates structured input using Rego and can be embedded in authorization or governance workflows. Advanced; the integrating system must enforce the decision. Test policy and failure behavior.

- **[Kyverno](https://kyverno.io/docs/)** — Kubernetes-native policy management for validation, mutation, generation, and related admission or background checks. Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests.

- **[OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/)** — Structure application-security verification requirements for platform-facing services. Intermediate to advanced; choose a version and applicable verification scope.

## Secrets and workload identity

Distinguish secret storage, encrypted configuration, identity federation, and workload identification. A synchronized Kubernetes Secret still needs access and encryption controls.

- **[HashiCorp Vault](https://developer.hashicorp.com/vault/docs)** — Secrets and credential-management capabilities, including policies, authentication methods, and supported secret engines. Advanced; sealing, recovery, access control, audit, and edition-specific features require design.

- **[External Secrets Operator](https://external-secrets.io/latest/)** — Kubernetes controllers that synchronize supported external secret stores into Kubernetes resources. Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets.

- **[SOPS](https://github.com/getsops/sops)** — Encryption of structured configuration files while retaining an editable file format and supporting configured key services. Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak.

- **[Keycloak](https://www.keycloak.org/documentation)** — Identity and access-management software for authentication, federation, and application identity integrations. Advanced; integration, federation, sessions, availability, and upgrades require specialist review.

- **[SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/)** — Workload identity specifications and concepts for identifying services across trust domains. Advanced; workload identity complements rather than replaces application authorization.

- **[AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/)** — Review managed secret storage, access, rotation, and service integrations. Intermediate; review IAM, rotation support, availability dependencies, and usage charges.

- **[Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/)** — Review managed secrets, keys, certificates, and access guidance. Intermediate; choose the relevant object and access model and plan recovery and billing.

- **[Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs)** — Review managed secret versions, access, and application integration. Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing.

## Metrics logs traces and alert delivery

OpenTelemetry instruments and transports signals; Prometheus, Loki, and Jaeger support different signal backends. Alertmanager routes alerts. Decide retention, sampling, tenancy, and operational ownership before composing them.

- **[OpenTelemetry](https://opentelemetry.io/docs/)** — Vendor-neutral APIs, SDKs, conventions, and collectors for producing and transporting telemetry. Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity.

- **[OpenTelemetry Collector](https://opentelemetry.io/docs/collector/)** — Review telemetry reception, processing, export, and deployment concerns. Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling.

- **[Prometheus](https://prometheus.io/docs/introduction/overview/)** — Metrics collection and querying with a time-series data model, PromQL, and alerting integrations. Intermediate; plan label cardinality, retention, storage, and availability.

- **[Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/)** — Alert routing, grouping, inhibition, and silencing for alerts from compatible sources. Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery.

- **[Grafana](https://grafana.com/docs/grafana/latest/)** — Build and govern dashboards and documented observability integrations. Intermediate; distinguish the operated software from cloud services and edition-specific capabilities.

- **[Grafana Loki](https://grafana.com/docs/loki/latest/)** — A log aggregation system with label-based indexing and query integration; evaluate retention, cardinality, and tenant access. Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance.

- **[Jaeger](https://www.jaegertracing.io/docs/)** — Distributed tracing software for following requests across services and investigating latency or errors. Intermediate; instrumentation coverage and sampling affect what can be observed.

## Network policy routing and service communication

Start with the packet path and trust boundaries. A service mesh is not required to enforce every policy, and a proxy is not a complete network design. eBPF means extended Berkeley Packet Filter.

- **[Cilium](https://docs.cilium.io/en/stable/)** — eBPF-based networking, security, and observability components for supported environments. Advanced; assess kernel, platform, deployment, and upgrade prerequisites.

- **[Calico](https://docs.tigera.io/calico/latest/about/)** — Workload networking and network-policy capabilities, including Kubernetes-focused installation and operating references. Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility.

- **[Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api)** — Compare Kubernetes traffic-routing APIs and implementation support. Intermediate; APIs require a compatible implementation. Check conformance and feature status.

- **[Envoy](https://www.envoyproxy.io/docs/envoy/latest/)** — An extensible proxy with routing, filtering, load-balancing, and telemetry features; integration and configuration ownership remain your responsibility. Advanced; this latest documentation branch identifies a development build. Choose documentation for the supported release you actually operate.

- **[Istio](https://istio.io/latest/docs/)** — Service-mesh traffic management, security, and telemetry for supported workloads. Advanced; evaluate supported data-plane modes, operational complexity, and application impact.

- **[Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/)** — Inspect capture and protocol-analysis workflows for network diagnosis. Intermediate; use packet captures only where authorized. Captures can expose credentials and personal or customer data; the retrieved guide identifies a development build.

## Performance failure testing and recovery

Choose tests that challenge a design assumption. Load tests, controlled failure experiments, and restore tools produce different kinds of evidence.

- **[Grafana k6](https://grafana.com/docs/k6/latest/)** — Scriptable load and performance testing with checks, metrics, and thresholds. Intermediate; model real traffic and service objectives. External targets need explicit test authorization.

- **[Locust](https://docs.locust.io/en/stable/)** — Python-based load generation in which test code models concurrent user behavior. Intermediate; the retrieved stable documentation identifies a development version. Confirm the installed release and its matching reference.

- **[Chaos Mesh](https://chaos-mesh.org/docs/)** — Explore Kubernetes failure-injection experiments. Advanced; use isolated environments and bounded experiments before considering production use.

- **[LitmusChaos](https://docs.litmuschaos.io/)** — Compare chaos experimentation and workflow capabilities. Advanced; assess permissions, compatibility, failure scope, and recovery controls.

- **[Velero documentation](https://velero.io/docs/)** — Kubernetes resource backup and restore tooling with storage integrations; verify application-data coverage separately. Advanced; rehearse restore and verify application data consistency, not only object recreation.

## Developer interfaces architecture records and cost

Developer portals, diagrams, and cost tools support decisions and user workflows. None replaces platform product ownership, a durable decision record, or actual billing reconciliation.

- **[Backstage](https://backstage.io/docs/overview/what-is-backstage/)** — A developer-portal framework with a software catalog, templates, and plugin integrations. Intermediate; catalog quality and plugin maintenance need ownership. A portal alone is not a complete platform.

- **[C4 model](https://c4model.com/)** — Describe software systems at useful levels of architectural abstraction. Foundation onward; diagrams communicate structure but do not establish operational correctness.

- **[Structurizr documentation](https://docs.structurizr.com/)** — Architecture-modeling tooling for generating consistent views from a shared system model. Intermediate; distinguish modeling tools and available deployment or service options.

- **[Mermaid](https://mermaid.js.org/intro/)** — Text-based diagram syntax and rendering for flow, sequence, and other supported diagram types. Foundation onward; renderer versions and supported diagram features differ between publishing platforms.

- **[Architecture Decision Records](https://adr.github.io/)** — Find guidance and resources for recording architectural decisions. Foundation onward; keep decisions connected to evidence and later changes.

- **[Infracost](https://www.infracost.io/docs/)** — Cost estimates and changes for supported infrastructure definitions before deployment. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees.

- **[OpenCost](https://opencost.io/docs/)** — Kubernetes cost allocation based on resource usage and pricing inputs. Intermediate; allocation assumptions, data quality, and shared costs need review.

- **[FinOps Framework](https://www.finops.org/framework/)** — Connect technology cost decisions with accountability and business value. Intermediate; apply using actual operating and billing evidence.

## Questions to settle before adopting a tool

Name its operator, failure impact, upgrade route, access model, data retention, and exit plan. Check whether you can meet its dependencies and support its recovery. Prefer a smaller coherent stack over overlapping components that no team owns.

## Continue exploring

[Compare tools](devops-architect-tools-and-technologies.md) · [Find official references](devops-architect-official-documentation.md) · [Explore architecture resources](devops-architect-architecture-resources.md) · [Find practical projects](devops-architect-labs-and-portfolio-projects.md)

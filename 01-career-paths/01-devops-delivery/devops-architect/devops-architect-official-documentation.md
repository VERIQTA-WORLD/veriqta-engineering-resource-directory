# DevOps architect: official documentation

[DevOps architect resource directory](README.md)

Use these references to validate a design against documented behavior. Start with the focused guide for your question, then use the surrounding documentation for configuration and limits. This page emphasizes authoritative implementation references; use the learning page for explanations, books, and courses. API means application programming interface. RBAC means role-based access control.

Many destinations use current, latest, or stable aliases. Select the product and release matching your environment, especially before upgrades, migration, or recovery.

## Find resources by topic

- [Workflow permissions runners and deployment approvals](#workflow-permissions-runners-and-deployment-approvals)
- [Infrastructure state backends modules and tests](#infrastructure-state-backends-modules-and-tests)
- [Kubernetes production boundaries](#kubernetes-production-boundaries)
- [Application packaging reconciliation and rollout control](#application-packaging-reconciliation-and-rollout-control)
- [Registry metadata signatures and admission checks](#registry-metadata-signatures-and-admission-checks)
- [Secrets identities and cloud authorization](#secrets-identities-and-cloud-authorization)
- [Telemetry transport storage and alerting](#telemetry-transport-storage-and-alerting)
- [Networking and diagnostic references](#networking-and-diagnostic-references)
- [Cloud operating foundations and managed Kubernetes](#cloud-operating-foundations-and-managed-kubernetes)
- [Backup restore and disaster recovery](#backup-restore-and-disaster-recovery)

## Workflow permissions runners and deployment approvals

Review the execution boundary around a pipeline: repository writes, forked contributions, runner access, cloud credentials, artifacts, and approvals. Hosted and self-hosted runners have different isolation responsibilities.

- **[GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions)** — Review runner trust, workflow access, and delivery credential exposure. Intermediate; public contributions and privileged jobs need distinct trust treatment.

- **[GitHub Actions: OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect)** — Explains federated workflow identity for obtaining short-lived credentials from supporting cloud providers. Public official concept guide; trust conditions still need to constrain repository, workflow, environment, and audience.

- **[GitHub Actions: Deployment environments](https://docs.github.com/en/actions/how-tos/deploy/configure-and-manage-deployments/manage-environments)** — Describes environment protection, deployment configuration, and environment secrets. Public official guide; feature availability depends on repository visibility and plan. Evaluate emergency access and approval ownership.

- **[GitLab Runner documentation](https://docs.gitlab.com/runner/)** — Design and operate execution infrastructure for GitLab pipelines. Advanced; executor choice changes isolation and maintenance responsibilities.

- **[Jenkins security guidance](https://www.jenkins.io/doc/book/security/)** — Review controller access, authorization, and security configuration. Advanced; plugin and agent boundaries also need review.

- **[Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/)** — Review hosted and self-hosted pipeline execution within Azure DevOps. Intermediate; agent pools, task permissions, and product access require review.

- **[AWS CodePipeline](https://docs.aws.amazon.com/codepipeline/)** — Review AWS-oriented delivery pipeline orchestration and service integrations. Intermediate; execution permissions, regions, integration costs, and artifact storage affect design.

- **[Google Cloud Build](https://cloud.google.com/build/docs)** — Evaluate Google Cloud build execution, configuration, and associated integrations. Intermediate; review worker options, service identities, billing, and network access.

## Infrastructure state backends modules and tests

State often contains sensitive information and controls resource ownership. Read backend behavior, locking where supported, access, migration, and testing before changing a shared provisioning service.

- **[Terraform state](https://developer.hashicorp.com/terraform/language/state)** — Understand infrastructure mappings and state behavior before designing shared automation. Intermediate; state may contain sensitive data. Protect storage and recovery procedures.

- **[Terraform backends](https://developer.hashicorp.com/terraform/language/backend)** — Compare state-backend configuration and documented backend capabilities. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike.

- **[Terraform testing](https://developer.hashicorp.com/terraform/language/tests)** — Review native test structures for modules and infrastructure workflows. Intermediate; some test arrangements create resources. Read execution and cleanup behavior first.

- **[Terraform style guide](https://developer.hashicorp.com/terraform/language/style)** — Covers conventions for readable and maintainable Terraform configuration. Public official guide; use it alongside module interfaces and testing rather than treating formatting as correctness.

- **[OpenTofu](https://opentofu.org/docs/)** — A declarative infrastructure engine with provider configuration, planning, and state workflows. Compare its own documentation and compatibility requirements before a migration. Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability.

- **[Pulumi IaC](https://www.pulumi.com/docs/iac/)** — Infrastructure definitions using supported programming languages, with an engine that tracks deployments and resource state. Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies.

- **[AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/)** — Review AWS resource provisioning, stack behavior, and change-management mechanisms. Intermediate; template support, stack boundaries, and rollback behavior must match the workload.

- **[Azure Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/)** — Evaluate declarative Azure infrastructure definitions and deployment workflows. Intermediate; provider-specific language and resource model. Review module, identity, and deployment-scope requirements.

- **[Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html)** — Agentless configuration and orchestration through inventories, modules, and playbooks. Intermediate; idempotency depends on modules and task design. Check collection and target compatibility.

- **[Ansible Vault](https://docs.ansible.com/ansible/latest/vault_guide/index.html)** — Review encrypted-data handling in configuration automation. Intermediate; encryption at rest does not prevent exposure after decryption.

- **[Packer](https://developer.hashicorp.com/packer/docs)** — Automated machine-image creation across supported builders; useful when you need reproducible base images rather than in-place host configuration. Intermediate; image builders require credentials, compute, and artifact lifecycle management.

- **[Crossplane](https://docs.crossplane.io/latest/)** — Kubernetes-based infrastructure control planes using providers and compositions to expose managed infrastructure APIs. Advanced; adds a control plane. Review provider permissions, reconciliation, ownership, and recovery.

## Kubernetes production boundaries

Use these focused references to evaluate cluster ownership, tenant isolation, authorization, network access, and workload behavior. Namespaces alone are not a complete isolation architecture.

- **[Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/)** — Compare production setup considerations and operating models. Advanced; managed services retain workload and configuration responsibilities.

- **[Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/)** — Review isolation choices and their limitations. Advanced; namespaces alone do not provide every required isolation boundary.

- **[Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)** — Design role-based access control for users, workloads, and controllers. Intermediate; assess escalation paths, broad grants, and service-account use.

- **[Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/)** — Review controls for cluster and workload operation. Intermediate; assign each control an owner and evidence source.

- **[Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/)** — Review traffic-control semantics and policy examples. Intermediate; enforcement depends on the network implementation and its supported behavior.

- **[Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)** — Review health-check semantics and configuration. Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies.

- **[Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/)** — Review requests, limits, scheduling, and resource constraints. Intermediate; workload measurements and node capacity are needed for useful settings.

- **[Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/)** — Understand availability during voluntary and involuntary disruptions. Intermediate; a disruption budget is not a universal guarantee against outages.

- **[Operating etcd clusters for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/)** — Explains etcd operation, backups, and control-plane considerations for Kubernetes. Advanced administration reference; managed control planes may hide or delegate these operations.

## Application packaging reconciliation and rollout control

Compare desired-state synchronization with rollout progression and traffic policy. Review controller ownership and resource conflicts when more than one component can change the same workload.

- **[Helm](https://helm.sh/docs/)** — Use the chart, template, values, and release references to validate the packaging and change behavior of a Kubernetes application. Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership.

- **[Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/)** — Customization of Kubernetes manifests through bases, overlays, patches, and transformations, without chart templating. Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling.

- **[Argo CD](https://argo-cd.readthedocs.io/en/stable/)** — Use the synchronization, application, and health references to review how Argo CD compares desired and live state, and what controls a deployment. Intermediate; define repository and cluster trust boundaries, controller availability, and recovery.

- **[Flux](https://fluxcd.io/flux/)** — Find controller, source, reconciliation, and bootstrap references for diagnosing or designing a Flux-managed environment. Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery.

- **[Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/)** — Kubernetes rollout control for canary and blue-green strategies, including traffic management and analysis integration. Advanced; traffic routing and metrics integrations determine what a rollout can actually verify.

- **[Flagger](https://docs.flagger.app/)** — Automated progressive delivery for Kubernetes workloads using metrics and supported traffic integrations. Advanced; verify supported providers and analysis behavior for the chosen environment.

- **[Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api)** — Compare Kubernetes traffic-routing APIs and implementation support. Intermediate; APIs require a compatible implementation. Check conformance and feature status.

- **[Istio](https://istio.io/latest/docs/)** — Service-mesh traffic management, security, and telemetry for supported workloads. Advanced; evaluate supported data-plane modes, operational complexity, and application impact.

## Registry metadata signatures and admission checks

Read how your tools obtain package metadata and verify evidence. Your design needs a trust policy, not simply an enabled scanner or a signed image. SBOM means software bill of materials.

- **[Harbor](https://goharbor.io/docs/)** — A container-image and artifact registry with access controls, replication, and vulnerability-scanning integrations. Intermediate; registry availability, storage, upgrades, and retention become platform responsibilities.

- **[JFrog Artifactory documentation](https://jfrog.com/help/r/jfrog-artifactory-documentation)** — Compare artifact repository capabilities across package formats and deployment options. Intermediate; commercial features and operating models vary. Check entitlement and storage requirements.

- **[Trivy](https://trivy.dev/latest/docs/)** — Evaluate vulnerability and configuration assessment within build and deployment workflows. Intermediate; findings need prioritization and exceptions. Scan success does not establish artifact safety.

- **[Syft](https://github.com/anchore/syft)** — A CLI and library for generating software bills of materials from container images and filesystems. Intermediate; inventory coverage depends on input and catalogers. Check downstream format requirements.

- **[Grype](https://github.com/anchore/grype)** — A vulnerability scanner matching image, filesystem, or software-bill-of-materials packages to vulnerability information. Intermediate; database freshness and package matching affect results. Establish a triage process.

- **[Sigstore Cosign](https://docs.sigstore.dev/cosign/signing/overview/)** — Artifact signing and verification tooling in the Sigstore ecosystem; signatures need explicit identity and trust policy to be useful. Advanced; define trusted identities, verification policy, and failure handling. A signature does not prove software quality.

- **[Kyverno](https://kyverno.io/docs/)** — Use admission, policy, rule, and operating references to check the behavior and exceptions of Kubernetes policy controls. Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests.

- **[Open Policy Agent](https://www.openpolicyagent.org/docs/)** — Find Rego, integration, testing, and operations references for the policy decision interface your system will enforce. Advanced; the integrating system must enforce the decision. Test policy and failure behavior.

- **[SLSA specification](https://slsa.dev/spec/)** — Read the specification to distinguish provenance and security guarantees from an informal claim that a build is trusted. Advanced; consult the relevant stable version and track specification changes.

- **[SPDX specifications](https://spdx.dev/specifications/)** — Review software bill of materials and associated information models. Advanced; select a supported specification version and validate producer-consumer compatibility.

- **[CycloneDX specification](https://cyclonedx.org/specification/overview/)** — Compare bill-of-materials formats and their documented scope. Advanced; choose formats around downstream consumers and required evidence.

- **[Open Container Initiative specifications](https://opencontainers.org/)** — Locate container image, runtime, and distribution specification work. Advanced; verify the exact specification and version relevant to the component.

## Secrets identities and cloud authorization

Match the authorization model to your actual principals and trust boundaries. Credential federation reduces long-lived secret use but does not remove the need for restricted trust conditions.

- **[HashiCorp Vault](https://developer.hashicorp.com/vault/docs)** — Find authentication, policy, secret-engine, and operating references for the credential boundary in your deployment system. Advanced; sealing, recovery, access control, audit, and edition-specific features require design.

- **[External Secrets Operator](https://external-secrets.io/latest/)** — Kubernetes controllers that synchronize supported external secret stores into Kubernetes resources. Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets.

- **[SOPS](https://github.com/getsops/sops)** — Encryption of structured configuration files while retaining an editable file format and supporting configured key services. Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak.

- **[Keycloak](https://www.keycloak.org/documentation)** — Identity and access-management software for authentication, federation, and application identity integrations. Advanced; integration, federation, sessions, availability, and upgrades require specialist review.

- **[SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/)** — Read the workload-identity concepts and specification links before assigning trust-domain or service-identity meaning to a design. Advanced; workload identity complements rather than replaces application authorization.

- **[AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)** — Review identity, permissions, credentials, and access-management guidance. Intermediate; combine with service-specific permissions and organization policies.

- **[Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/)** — Review application identity, authentication, and integration concepts. Intermediate to advanced; application identity and infrastructure authorization are separate concerns.

- **[Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview)** — Review Google Cloud access-control concepts and resource relationships. Intermediate; validate actual permissions at the required resource scope.

- **[AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/)** — Review managed secret storage, access, rotation, and service integrations. Intermediate; review IAM, rotation support, availability dependencies, and usage charges.

- **[Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/)** — Review managed secrets, keys, certificates, and access guidance. Intermediate; choose the relevant object and access model and plan recovery and billing.

- **[Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs)** — Review managed secret versions, access, and application integration. Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing.

- **[OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html)** — Review identity-layer protocol requirements and flows. Advanced; distinguish authentication from resource authorization and verify implementation guidance.

- **[OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html)** — Review current protocol security recommendations for OAuth implementations. Advanced; applies alongside the relevant OAuth specifications and implementation documentation.

## Telemetry transport storage and alerting

Use the Collector reference for pipelines and processing, and backend references for storage, queries, retention, and operations. A signal reaching a collector does not establish that it is available to your responders.

- **[OpenTelemetry Collector](https://opentelemetry.io/docs/collector/)** — Find receiver, processor, exporter, and operating guidance for the telemetry path connecting applications with backends. Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling.

- **[Prometheus](https://prometheus.io/docs/introduction/overview/)** — Metrics collection and querying with a time-series data model, PromQL, and alerting integrations. Intermediate; plan label cardinality, retention, storage, and availability.

- **[Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/)** — Alert routing, grouping, inhibition, and silencing for alerts from compatible sources. Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery.

- **[Grafana](https://grafana.com/docs/grafana/latest/)** — Build and govern dashboards and documented observability integrations. Intermediate; distinguish the operated software from cloud services and edition-specific capabilities.

- **[Grafana Loki](https://grafana.com/docs/loki/latest/)** — A log aggregation system with label-based indexing and query integration; evaluate retention, cardinality, and tenant access. Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance.

- **[Jaeger](https://www.jaegertracing.io/docs/)** — Distributed tracing software for following requests across services and investigating latency or errors. Intermediate; instrumentation coverage and sampling affect what can be observed.

## Networking and diagnostic references

Protocol specifications explain semantics; component references explain an implementation. Use both when troubleshooting routing, authentication, retries, or TLS termination. TLS means Transport Layer Security.

- **[Cilium](https://docs.cilium.io/en/stable/)** — eBPF-based networking, security, and observability components for supported environments. Advanced; assess kernel, platform, deployment, and upgrade prerequisites.

- **[Calico](https://docs.tigera.io/calico/latest/about/)** — Workload networking and network-policy capabilities, including Kubernetes-focused installation and operating references. Advanced; distinguish Calico documentation from related commercial offerings and verify deployment compatibility.

- **[Envoy](https://www.envoyproxy.io/docs/envoy/latest/)** — An extensible proxy with routing, filtering, load-balancing, and telemetry features; integration and configuration ownership remain your responsibility. Advanced; this latest documentation branch identifies a development build. Choose documentation for the supported release you actually operate.

- **[Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/)** — Inspect capture and protocol-analysis workflows for network diagnosis. Intermediate; use packet captures only where authorized. Captures can expose credentials and personal or customer data; the retrieved guide identifies a development build.

- **[HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html)** — Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy.

- **[TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/)** — Review transport-security protocol requirements and behavior. Advanced; certificate lifecycle and application configuration require additional guidance.

## Cloud operating foundations and managed Kubernetes

These provider references help you evaluate account foundations and runtime decisions. Read them as provider-specific implementations, not as evidence that all providers have equivalent controls.

- **[AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/)** — Explore governed multi-account foundations and service operations. Advanced; organizational decisions, identity, networking, and account policies remain essential.

- **[Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)** — Review enterprise-scale platform foundations and design areas. Advanced; tailoring and operating ownership are required before deployment.

- **[Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations)** — Review an opinionated approach to organizational cloud foundations. Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions.

- **[Amazon EKS best practices](https://docs.aws.amazon.com/eks/latest/best-practices/introduction.html)** — Review Kubernetes workload and cluster-design guidance for EKS. Advanced; EKS-specific assumptions must be separated from general Kubernetes advice.

- **[AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks)** — Examine a documented infrastructure baseline for an Azure Kubernetes Service cluster. Advanced; adapt identity, network, availability, and cost choices to requirements.

- **[AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)** — Review AWS workload decisions and architectural trade-offs. Intermediate to advanced; provider-specific framework, not an independent compliance audit.

- **[Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/)** — Structure Azure workload reviews around documented quality concerns. Intermediate to advanced; tailor review depth to business and workload needs.

- **[Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework)** — Structure Google Cloud workload architecture reviews. Intermediate to advanced; provider-specific assumptions require interpretation.

## Backup restore and disaster recovery

Define recovery time and recovery point objectives before selecting a recovery procedure. RTO is the acceptable restoration time; RPO is the acceptable data-loss window. Evaluate dependent services and application data as well as infrastructure.

- **[Velero documentation](https://velero.io/docs/)** — Find installation, backup, restore, storage-integration, and troubleshooting references for a defined Kubernetes recovery scope. Advanced; rehearse restore and verify application data consistency, not only object recreation.

- **[PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html)** — Review PostgreSQL backup approaches and restoration references before choosing evidence for an application-data recovery requirement. Advanced; use documentation matching the deployed database version and test restored data.

- **[AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html)** — Compare recovery strategies and resilience considerations for AWS workloads. Advanced; define recovery time and recovery point objectives and test the complete workload.

- **[Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview)** — Locate Azure disaster-recovery concepts and planning guidance. Advanced; service support and workload dependencies determine feasible recovery objectives.

- **[Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide)** — Review recovery planning, objectives, and scenario selection. Advanced; test identity, configuration, data, and traffic restoration together.



## Continue exploring

[Compare tools](devops-architect-tools-and-technologies.md) · [Find official references](devops-architect-official-documentation.md) · [Explore architecture resources](devops-architect-architecture-resources.md) · [Find practical projects](devops-architect-labs-and-portfolio-projects.md)

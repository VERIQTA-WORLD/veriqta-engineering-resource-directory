# DevOps automation engineer: tool directory

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Scripts, structured data, and task entry points

Choose tools around the formats and execution environments you actually maintain. Bash and PowerShell have different language and error models. A task runner organizes operations; the script or service still needs clear failure semantics.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Python tutorial](https://docs.python.org/3/tutorial/) | Read the language tutorial before maintaining automation that parses data, calls services, or manages files. | Foundation in Python; assumes basic programming knowledge. Publicly readable; use an isolated virtual environment and match the installed interpreter. |
| [GNU Bash manual](https://www.gnu.org/software/bash/manual/bash.html) | Check expansion, quoting, pipelines, redirection, and exit behavior when reviewing shell scripts. | Foundation to advanced; publicly readable GNU Bash reference. Other shells have different behavior. Source retrieval was blocked during this review; availability and the current document remain pending verification. |
| [PowerShell documentation](https://learn.microsoft.com/en-us/powershell/) | Find language, scripting, remoting, and administration references for PowerShell automation. | Foundation onward; publicly readable. Distinguish PowerShell releases and Windows PowerShell; platform availability varies by module. |
| [jq manual](https://jqlang.org/manual/) | Inspect and transform JSON returned by command-line clients and infrastructure APIs. | Foundation onward; publicly readable manual. Validate missing fields rather than assuming one provider response shape. |
| [Mike Farah yq](https://mikefarah.gitbook.io/yq/) | Read and update structured configuration with the documented yq implementation. | Intermediate; public documentation. Several unrelated utilities share the name yq; check the actual implementation. |
| [Task](https://taskfile.dev/) | Compare a task runner for repeatable repository commands and developer entry points. | Foundation onward; public documentation. A task runner does not make destructive commands safe or idempotent. |
| [Requests](https://requests.readthedocs.io/en/latest/) | Implement Python HTTP clients using documented sessions, authentication, and request interfaces. | Intermediate; public documentation. Set explicit timeouts and handle response semantics; do not log tokens. |
| [curl documentation](https://curl.se/docs/) | Find official command-line, protocol, TLS, and library references for HTTP and other supported transfers. | Foundation onward; public reference collection. Inspect quoting, output, certificates, and failure behavior before using curl in automation. |
| [pre-commit](https://pre-commit.com/) | Run repository checks consistently before changes enter the delivery workflow. | Foundation onward; public documentation. Pin and review hooks, and enforce important checks in CI as well. |

## Testing the automation itself

Use static analysis, unit tests, configuration scenarios, and integration tests together. Each detects different failures; none makes a privileged script safe merely by passing.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [ShellCheck](https://www.shellcheck.net/) | Find common shell-script mistakes before an operational script is shipped. | Public reference. Foundation onward; web interface and project links are public. Do not paste secrets or private scripts into a hosted checker. |
| [Bats-core](https://bats-core.readthedocs.io/en/stable/) | Write repeatable shell tests around observable outputs and exit statuses. | Intermediate; public project documentation. Tests need disposable fixtures when scripts alter systems. |
| [pytest](https://docs.pytest.org/en/stable/) | Test Python automation with fixtures, assertions, parametrization, and temporary environments. | Intermediate; public project documentation. Mocks cannot establish that a live provider behaves correctly. |
| [Pester documentation](https://pester.dev/docs/quick-start) | Write and run tests for PowerShell code using the project's introductory documentation. | Intermediate; public guide. Tests that call real systems need disposable targets and explicit cleanup. |
| [Ansible Lint](https://docs.ansible.com/projects/lint/) | Check playbooks and roles for documented quality and maintainability rules. | Intermediate; public documentation. Lint passes do not establish desired-state correctness or successful recovery. |
| [Ansible Molecule](https://docs.ansible.com/projects/molecule/) | Evaluate scenarios for developing and testing Ansible collections, playbooks, and roles. | Intermediate; public documentation. Scenario drivers and targets determine infrastructure, privileges, and cleanup requirements. |
| [Testcontainers](https://testcontainers.com/guides/) | Find guides for container-backed integration test dependencies. | Public reference. Intermediate; runtime and language-library requirements vary. Tests still need meaningful assertions. |

## Provisioning, images, and configuration

Keep provisioning, machine-image construction, and configuration ownership distinct. Test convergence and define what happens after an interrupted run.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Public reference. Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Public reference. Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Public reference. Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Public reference. Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Packer](https://developer.hashicorp.com/packer/docs) | Build repeatable machine images and separate image creation from runtime configuration. | Public reference. Intermediate; image builders require credentials, compute, and artifact lifecycle management. |
| [cloud-init documentation](https://cloudinit.readthedocs.io/en/latest/) | Compare first-boot provisioning, datasource handling, and machine initialization workflows. | Intermediate; public documentation. Instance metadata, credentials, and repeated initialization require careful review. |
| [Vagrant documentation](https://developer.hashicorp.com/vagrant/docs) | Evaluate reproducible local virtual-machine environments for host and configuration experiments. | Foundation onward; public documentation. A supported virtualization provider and sufficient local resources are required. |

## Execution engines and reusable delivery

Evaluate how workflows handle inputs, permissions, artifacts, concurrency, cancellation, and retries. Kubernetes workflow engines introduce a cluster operating dependency.

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

## Deployment reconciliation and packaging

Use these when the automation produces container workloads. Reconciliation and rollout analysis are separate controls.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Public reference. Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Public reference. Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Public reference. Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | Compare application synchronization, repository integration, and Kubernetes deployment management. | Public reference. Intermediate; define repository and cluster trust boundaries, controller availability, and recovery. |
| [Flux](https://fluxcd.io/flux/) | Evaluate controller-based GitOps reconciliation for Kubernetes sources and workloads. | Public reference. Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Public reference. Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |

## Credentials, policy, and artifact evidence

Minimize long-lived privileges. Check both policy evaluation and the system that enforces the decision.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Public reference. Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [SOPS](https://github.com/getsops/sops) | Review encrypted configuration-file workflows with supported key services. | Public reference. Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak. |
| [External Secrets Operator](https://external-secrets.io/latest/) | Evaluate synchronization between external secret stores and Kubernetes. | Public reference. Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets. |
| [Open Policy Agent](https://www.openpolicyagent.org/docs/) | Evaluate general policy evaluation and integration patterns. | Public reference. Advanced; the integrating system must enforce the decision. Test policy and failure behavior. |
| [Kyverno](https://kyverno.io/docs/) | Assess Kubernetes policy validation, mutation, and other documented policy capabilities. | Public reference. Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests. |
| [Sigstore Cosign](https://docs.sigstore.dev/cosign/signing/overview/) | Design artifact signing and verification workflows. | Public reference. Advanced; define trusted identities, verification policy, and failure handling. A signature does not prove software quality. |
| [Syft](https://github.com/anchore/syft) | Generate software bill of materials (SBOM) data from supported artifacts. | Public reference. Intermediate; inventory coverage depends on input and catalogers. Check downstream format requirements. |
| [Grype](https://github.com/anchore/grype) | Evaluate vulnerability matching against images, filesystems, or supported SBOM inputs. | Public reference. Intermediate; database freshness and package matching affect results. Establish a triage process. |
| [Trivy](https://trivy.dev/latest/docs/) | Evaluate vulnerability and configuration assessment within build and deployment workflows. | Public reference. Intermediate; findings need prioritization and exceptions. Scan success does not establish artifact safety. |

## Execution visibility and resilience checks

Make run identifiers, outcomes, and failure stages visible without recording sensitive inputs. Use load and failure tools only against authorized test targets.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Public reference. Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Public reference. Intermediate; plan label cardinality, retention, storage, and availability. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Public reference. Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Public reference. Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Public reference. Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Public reference. Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Public reference. Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Public reference. Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |

## Continue browsing

[Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

# DevOps engineer: official documentation

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Delivery definitions and execution boundaries

Use exact references to diagnose why a workflow did not produce or deploy the intended artifact. Check runner identity, inputs, and permissions before rerunning.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub reusable workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) | Define shared workflow interfaces, inputs, secrets, and calls between repositories. | Intermediate; public documentation. Review secret propagation, environment behavior, permissions, and version pinning. |
| [GitHub workflow artifacts](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflow-artifacts) | Understand how outputs move between jobs and remain available after workflow execution. | Foundation onward; public documentation. Retention, access, and storage limits depend on service settings and account terms. |
| [GitHub self-hosted runners](https://docs.github.com/en/actions/concepts/runners/self-hosted-runners) | Assess responsibility for runner machines and their execution environments. | Intermediate; public documentation. Untrusted jobs, persistent workspaces, network reachability, and patching require deliberate controls. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review workflow, dependency, runner, and credential security considerations. | Public reference. Intermediate; apply the guidance to the repository trust model and runner arrangement. |
| [GitLab CI/CD YAML reference](https://docs.gitlab.com/ci/yaml/) | Check pipeline syntax, job relationships, artifacts, and configuration keywords. | Intermediate; public reference. Match examples to the deployed GitLab version and available features. |
| [GitLab Runner documentation](https://docs.gitlab.com/runner/) | Design and operate execution infrastructure for GitLab pipelines. | Public reference. Advanced; executor choice changes isolation and maintenance responsibilities. |
| [Jenkins Pipeline syntax](https://www.jenkins.io/doc/book/pipeline/syntax/) | Review declarative and scripted Pipeline constructs in maintained build definitions. | Intermediate; public reference. Plugin and agent availability affect which steps a controller can execute. |
| [Jenkins security guidance](https://www.jenkins.io/doc/book/security/) | Review controller access, authorization, and security configuration. | Public reference. Advanced; plugin and agent boundaries also need review. |

## Infrastructure plans and configuration changes

Read change and state behavior before importing, replacing, or correcting resources. Test playbook targeting and error behavior in a controlled environment.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Public reference. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Terraform lifecycle rules](https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle) | Review replacement ordering, destruction protection, and ignored changes in resource definitions. | Intermediate; public language reference. Provider behavior and dependency relationships affect the actual change. |
| [Terraform testing](https://developer.hashicorp.com/terraform/language/tests) | Review native test structures for modules and infrastructure workflows. | Public reference. Intermediate; some test arrangements create resources. Read execution and cleanup behavior first. |
| [Ansible inventory guide](https://docs.ansible.com/projects/ansible/latest/inventory_guide/intro_inventory.html) | Organize hosts, groups, variables, and inventory sources for controlled targeting. | Intermediate; public reference. Protect inventory data and test precedence before widening the target group. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) | Review simulated changes and configuration differences before a deployment. | Intermediate; public reference. Module support varies, explicit task settings can allow changes, and diff output may expose secrets. |
| [Ansible execution strategies](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_strategies.html) | Select batching, parallelism, and task ordering for a fleet change. | Intermediate; publicly readable. More parallel execution can increase blast radius and load on shared services. |

## Workload behavior and cluster operations

Read these alongside the documentation for the cluster distribution or managed service in use. Application probes, resource settings, networking, and storage interact.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) | Review health-check semantics and configuration. | Public reference. Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Public reference. Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Public reference. Intermediate; a disruption budget is not a universal guarantee against outages. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Public reference. Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | Design role-based access control for users, workloads, and controllers. | Public reference. Intermediate; assess escalation paths, broad grants, and service-account use. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Kubernetes horizontal pod autoscaling](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/) | Study metric-based workload scaling and controller behavior. | Intermediate; public reference. Scaling replicas does not necessarily resolve a dependency bottleneck or supply node capacity. |
| [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) | Locate workload debugging references for deployment and runtime failures. | Public reference. Intermediate; establish scope before applying changes. Read permissions and command effects. |

## Telemetry, identity, and cloud controls

Use provider and project references for the installed environment rather than copying settings across clouds.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Public reference. Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Public reference. Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Public reference. Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Public reference. Intermediate; validate actual permissions at the required resource scope. |
| [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) | Review workload decisions across operational, reliability, security, performance, cost, and sustainability concerns. | Public reference. Intermediate to advanced; AWS-specific guidance. Adapt recommendations to requirements. |
| [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/) | Review Azure workload architecture and quality trade-offs. | Public reference. Intermediate to advanced; assess workload context rather than treating guidance as a universal checklist. |
| [Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework) | Review Google Cloud architecture guidance across its documented pillars. | Public reference. Intermediate to advanced; provider-specific capabilities and assumptions need review. |

## Continue browsing

[Tool directory](toolkit.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

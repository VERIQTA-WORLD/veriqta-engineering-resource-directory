# DevOps engineer: production responsibilities and operational resources

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Produce and promote the intended artifact

Keep build outputs traceable and review which identity can publish or deploy them. A successful job is not proof that the correct artifact reached the correct environment.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub workflow artifacts](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflow-artifacts) | Understand how outputs move between jobs and remain available after workflow execution. | Foundation onward; public documentation. Retention, access, and storage limits depend on service settings and account terms. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review runner trust, workflow access, and delivery credential exposure. | Intermediate; public contributions and privileged jobs need distinct trust treatment. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Public reference. Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |
| [Release engineering](https://sre.google/sre-book/release-engineering/) | Study an original account of build, release, and deployment engineering. | Public reference. Intermediate to advanced; Google-specific practices require adaptation. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Public reference. Advanced; comparison quality and observation design determine whether a canary is informative. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Public reference. Advanced; official PDF. Application and schema compatibility must be tested in your own system. |

## Maintain configuration and workload behavior

Investigate drift, failed targets, resource pressure, and unhealthy workloads using evidence from the affected layer. Avoid broad corrective changes before the failure is understood.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) | Review simulated changes and configuration differences before a deployment. | Intermediate; public reference. Module support varies, explicit task settings can allow changes, and diff output may expose secrets. |
| [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) | Locate workload debugging references for deployment and runtime failures. | Public reference. Intermediate; establish scope before applying changes. Read permissions and command effects. |
| [Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) | Review health-check semantics and configuration. | Public reference. Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Public reference. Intermediate; workload measurements and node capacity are needed for useful settings. |
| [cloud-init debugging guide](https://cloudinit.readthedocs.io/en/latest/howto/debugging.html) | Find status and log evidence when instance initialization fails. | Intermediate; public guide. Logs and rendered user data can contain sensitive information. |

## Operate alerts and incidents

Connect alerts to service objectives, an owner, diagnostic resources, and recovery actions. Preserve an incident timeline and use postmortems to improve the system.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Public reference. Intermediate; useful measures depend on service behavior and user expectations. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Public reference. Advanced; validate alert behavior against real traffic and responder capacity. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Public reference. Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Public reference. Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Public reference. Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Public reference. Advanced; validate containment strategies with bounded tests and measurements. |

## Exercise recovery and control operational cost

Review both backup availability and actual restore behavior. Include delivery services, retained artifacts, telemetry, and idle infrastructure in cost review.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Jenkins backup and restore](https://www.jenkins.io/doc/book/system-administration/backing-up/) | Plan recovery of controller configuration and data rather than only rebuilding agents. | Intermediate; public operating guide. Protect backed-up secrets and exercise restore in an isolated environment. |
| [Velero documentation](https://velero.io/docs/) | Review Kubernetes backup and restore mechanisms and provider requirements. | Public reference. Advanced; rehearse restore and verify application data consistency, not only object recreation. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Public reference. Advanced; use documentation matching the deployed database version and test restored data. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Public reference. Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Public reference. Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Public reference. Advanced; test identity, configuration, data, and traffic restoration together. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Public reference. Intermediate; cost work requires billing and usage data, not estimates alone. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Public reference. Intermediate; allocation assumptions, data quality, and shared costs need review. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Standards and frameworks](standards-and-frameworks.md)

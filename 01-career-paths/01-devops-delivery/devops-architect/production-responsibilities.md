# Production responsibilities and operational resources

Resources for connecting architecture decisions to delivery safety, reliability, security, recovery, and cost. The architect works with service owners and operators to define boundaries and evidence; responsibilities depend on the organization.

Use the links to review a concrete system. Record the decision, accountable owner, relevant service objective, failure behavior, and verification evidence. Tools used to investigate these concerns are grouped in the [toolkit](toolkit.md).

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

## Delivery safety and control-plane ownership

The architect defines how changes move, who can authorize them, what evidence is required, and how the delivery system itself is recovered. Use these resources to review that design with its operators.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review runner trust, workflow access, and delivery credential exposure. | Intermediate; public contributions and privileged jobs need distinct trust treatment. |
| [Release engineering](https://sre.google/sre-book/release-engineering/) | Study an original account of build, release, and deployment engineering. | Intermediate to advanced; Google-specific practices require adaptation. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Advanced; official PDF. Application and schema compatibility must be tested in your own system. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |

## Reliability targets, alerting, and incident learning

Connect architecture to measurable service behavior. Define who responds, which dependencies matter, and how recovery is verified.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |

## Failure containment and dependency behavior

Use these references when reviewing retries, overload, deployment boundaries, and cascades. Document how the application behaves when dependencies are slow or unavailable.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) | Locate workload debugging references for deployment and runtime failures. | Intermediate; establish scope before applying changes. Read permissions and command effects. |

## Recovery, security, cost, and evidence

Agree recovery objectives and required evidence before an outage. Track ownership of restored data, identities, artifacts, configuration, and supporting services.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Velero documentation](https://velero.io/docs/) | Review Kubernetes backup and restore mechanisms and provider requirements. | Advanced; rehearse restore and verify application data consistency, not only object recreation. |
| [Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/) | Review controls for cluster and workload operation. | Intermediate; assign each control an owner and evidence source. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Intermediate; cost work requires billing and usage data, not estimates alone. |
| [Cloudflare outage report, July 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/) | Study an original account of a software change, resource exhaustion, and recovery. | Advanced; historical incident, not a description of the company's current architecture. |
| [GitLab database outage report, January 2017](https://about.gitlab.com/blog/2017/02/01/gitlab-dot-com-database-incident/) | Study an original recovery incident and the importance of tested backup procedures. | Advanced; historical incident. Distinguish recorded facts from assumptions about present systems. |

## Provider-specific recovery planning

Use recovery guidance for the selected environment and prove the end-to-end outcome with its service owners. Replication, backup, failover, and restore are different mechanisms.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Advanced; test identity, configuration, data, and traffic restoration together. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Advanced; use documentation matching the deployed database version and test restored data. |

---

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

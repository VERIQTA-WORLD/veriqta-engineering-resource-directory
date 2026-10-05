# DevOps consultant: production responsibilities and operational resources

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Establish an evidence-based baseline

Agree what delivery and reliability measures mean for the service. Correlate metrics with interviews and workflow mapping before recommending tooling or organization changes.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [DORA software delivery metrics guide](https://dora.dev/guides/dora-metrics/) | Select delivery measurements and interpret them as improvement signals. | Foundation onward; public research-program guidance. Define measurement context; avoid using aggregate metrics to rank individual engineers. |
| [DORA value stream mapping guide](https://dora.dev/guides/value-stream-management/) | Locate workflow delays and connect an improvement proposal to delivery flow. | Intermediate; public guide. Validate the mapping with the people doing the work rather than inferring delays from tool data alone. |
| [DORA capabilities](https://dora.dev/capabilities/) | Find research-informed delivery and organizational capability references. | Public reference. Intermediate; assess evidence and local constraints before prioritizing changes. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Public reference. Intermediate; useful measures depend on service behavior and user expectations. |

## Review release and platform risk

Trace who can change code, pipeline definitions, credentials, and infrastructure. Connect proposed changes to rollout evidence, rollback compatibility, and operational ownership.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review runner trust, workflow access, and delivery credential exposure. | Intermediate; public contributions and privileged jobs need distinct trust treatment. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Public reference. Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |
| [Release engineering](https://sre.google/sre-book/release-engineering/) | Study an original account of build, release, and deployment engineering. | Public reference. Intermediate to advanced; Google-specific practices require adaptation. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Public reference. Advanced; comparison quality and observation design determine whether a canary is informative. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Public reference. Advanced; official PDF. Application and schema compatibility must be tested in your own system. |
| [Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/) | Review controls for cluster and workload operation. | Public reference. Intermediate; assign each control an owner and evidence source. |

## Review reliability and recovery claims

Compare incident handling and tested recovery with the agreed service objectives. Ask for restore evidence rather than assuming a configured backup proves recoverability.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Public reference. Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Public reference. Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Public reference. Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Public reference. Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Public reference. Advanced; test identity, configuration, data, and traffic restoration together. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Public reference. Advanced; use documentation matching the deployed database version and test restored data. |

## Plan improvement, ownership, and handover

State the expected outcome, implementation owner, operating cost, and evidence of acceptance. Use historical incidents to examine mechanisms, not to invent causes or assign blame.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [The evolving SRE engagement model](https://sre.google/workbook/engagement-model/) | Understand service engagement, collaboration, and operational responsibility boundaries. | Intermediate; public workbook chapter. Organizational labels and staffing models vary; explicitly agree ownership locally. |
| [Reliable product launches](https://sre.google/sre-book/reliable-product-launches/) | Compare readiness review, launch coordination, and production-risk reduction. | Intermediate; public book chapter. Select checks appropriate to the service and the people who own it. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Public reference. Intermediate; cost work requires billing and usage data, not estimates alone. |
| [Cloudflare outage report, July 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/) | Study an original account of a software change, resource exhaustion, and recovery. | Public reference. Advanced; historical incident, not a description of the company's current architecture. |
| [GitLab database outage report, January 2017](https://about.gitlab.com/blog/2017/02/01/gitlab-dot-com-database-incident/) | Study an original recovery incident and the importance of tested backup procedures. | Public reference. Advanced; historical incident. Distinguish recorded facts from assumptions about present systems. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Standards and frameworks](standards-and-frameworks.md)

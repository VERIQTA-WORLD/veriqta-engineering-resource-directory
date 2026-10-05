# Cloud reliability engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Separate provider events from workload failures](#separate-provider-events-from-workload-failures)
- [Maintain recovery capacity and safe changes](#maintain-recovery-capacity-and-safe-changes)
- [Exercise data and regional recovery](#exercise-data-and-regional-recovery)
- [Operate objectives, incidents, and cost](#operate-objectives-incidents-and-cost)

## Separate provider events from workload failures

Correlate customer symptoms, your telemetry, provider health, and recent changes. Preserve evidence even when a provider event is a plausible explanation.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Health documentation](https://docs.aws.amazon.com/health/) | Find provider-event visibility and account-specific health information guidance. | Intermediate; public documentation. Provider status is one signal; it does not replace your own service measurements. |
| [Azure Service Health documentation](https://learn.microsoft.com/en-us/azure/service-health/) | Review provider incident, maintenance, and advisory visibility for Azure workloads. | Foundation onward; public reference. Access to account-specific information requires appropriate subscription permissions. |
| [Google Cloud Service Health documentation](https://cloud.google.com/service-health/docs/overview) | Find provider health and incident visibility guidance for cloud operations. | Intermediate; public reference. Compare provider events with workload telemetry and dependency evidence. |
| [Monitoring distributed systems](https://sre.google/sre-book/monitoring-distributed-systems/) | Select service signals and distinguish user-facing symptoms from internal causes. | Foundation to intermediate; public book chapter. Instrumentation coverage and missing traffic affect interpretation. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |

## Maintain recovery capacity and safe changes

Check quotas, useful capacity after a failure, deployment compatibility, identity, and the infrastructure state used by recovery.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Advanced; official PDF. Application and schema compatibility must be tested in your own system. |
| [AWS operational guidance: safe deployment strategies](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/ops_mit_deploy_risks_deploy_mgmt_sys.html) | Compare progressive deployment, observation, and recovery practices in AWS operational guidance. | Intermediate; public vendor review guidance. Select mechanisms suitable for the actual workload and preserve evidence of rollback behavior. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Intermediate; combine with service-specific permissions and organization policies. |

## Exercise data and regional recovery

Validate the recoverability of configuration, credentials, data, traffic, and dependencies together. Backups and replicas address different failures.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview) | Locate Azure disaster-recovery concepts and planning guidance. | Advanced; service support and workload dependencies determine feasible recovery objectives. |
| [Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide) | Review recovery planning, objectives, and scenario selection. | Advanced; test identity, configuration, data, and traffic restoration together. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Velero documentation](https://velero.io/docs/) | Review Kubernetes backup and restore mechanisms and provider requirements. | Advanced; rehearse restore and verify application data consistency, not only object recreation. |

## Operate objectives, incidents, and cost

Keep alerts actionable, incident roles clear, and recovery evidence connected to expenditure and service impact.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) | Compare alerting approaches based on reliability objectives and budget consumption. | Advanced; validate alert behavior against real traffic and responder capacity. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Example error budget policy](https://sre.google/workbook/error-budget-policy/) | Find a concrete example of how reliability evidence can influence change decisions. | Intermediate; public appendix. A policy needs agreed authority, exceptions, and a measured service boundary. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Intermediate; cost work requires billing and usage data, not estimates alone. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [AWS S3 service disruption summary, 2017](https://aws.amazon.com/message/41926/) | Read the provider's original account of a historical regional service disruption. | Intermediate; public historical report. Its documented scope and corrective actions are specific to that event. |

[Browse the other collections](README.md#resource-collections)

# Platform reliability engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Define platform service objectives and ownership](#define-platform-service-objectives-and-ownership)
- [Operate shared control planes and delivery services](#operate-shared-control-planes-and-delivery-services)
- [Manage change, isolation, and recovery](#manage-change-isolation-and-recovery)
- [Keep telemetry, incidents, and capacity usable](#keep-telemetry-incidents-and-capacity-usable)
- [Maintain response coordination and escalation](#maintain-response-coordination-and-escalation)

## Define platform service objectives and ownership

Track the complete user journey, shared dependencies, support agreement, and error budget. Catalog metadata should identify a responsible owner and usable operating resources.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Example SLO document](https://sre.google/workbook/slo-document/) | Review a worked document connecting service indicators, targets, and measurement details. | Foundation onward; public appendix. Adapt the scope and data sources instead of copying its numbers. |
| [Example error budget policy](https://sre.google/workbook/error-budget-policy/) | Find a concrete example of how reliability evidence can influence change decisions. | Intermediate; public appendix. A policy needs agreed authority, exceptions, and a measured service boundary. |
| [Backstage software catalog](https://backstage.io/docs/features/software-catalog/) | Model service ownership and metadata discovery for a developer portal. | Intermediate; public documentation. Catalog metadata is not proof that a service meets production controls. |
| [The evolving SRE engagement model](https://sre.google/workbook/engagement-model/) | Understand service engagement, collaboration, and operational responsibility boundaries. | Intermediate; public workbook chapter. Organizational labels and staffing models vary; explicitly agree ownership locally. |
| [Reliable product launches](https://sre.google/sre-book/reliable-product-launches/) | Compare readiness review, launch coordination, and production-risk reduction. | Intermediate; public book chapter. Select checks appropriate to the service and the people who own it. |

## Operate shared control planes and delivery services

Investigate API availability, queueing, controller progress, runner health, credentials, storage, and reconciliation state before blaming the consuming service.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) | Locate workload debugging references for deployment and runtime failures. | Intermediate; establish scope before applying changes. Read permissions and command effects. |
| [Operating etcd for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/) | Find etcd configuration, maintenance, and recovery guidance for self-managed control planes. | Advanced; public task guide. Quorum changes and restores affect cluster state; managed providers have separate responsibility boundaries. |
| [GitHub self-hosted runners](https://docs.github.com/en/actions/concepts/runners/self-hosted-runners) | Assess responsibility for runner machines and their execution environments. | Intermediate; public documentation. Untrusted jobs, persistent workspaces, network reachability, and patching require deliberate controls. |
| [Jenkins backup and restore](https://www.jenkins.io/doc/book/system-administration/backing-up/) | Plan recovery of controller configuration and data rather than only rebuilding agents. | Intermediate; public operating guide. Protect backed-up secrets and exercise restore in an isolated environment. |
| [Terraform state](https://developer.hashicorp.com/terraform/language/state) | Understand infrastructure mappings and state behavior before designing shared automation. | Intermediate; state may contain sensitive data. Protect storage and recovery procedures. |
| [Harbor](https://goharbor.io/docs/) | Assess an operated container registry and its project, security, and replication capabilities. | Intermediate; registry availability, storage, upgrades, and retention become platform responsibilities. |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |

## Manage change, isolation, and recovery

Validate upgrades and tenant effects, preserve infrastructure state and recovery material, and test the recovery of the platform's own dependencies.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubeadm cluster upgrades](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/) | Review documented version transitions and component order for kubeadm-managed clusters. | Advanced; public procedure. This is not the upgrade procedure for every managed Kubernetes service; back up and follow the supported version path. |
| [Kubernetes node drain](https://kubernetes.io/docs/tasks/administer-cluster/safely-drain-node/) | Understand workload eviction during node maintenance. | Intermediate; public task guide. Draining changes availability; disruption budgets, local data, and unmanaged pods affect behavior. |
| [Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/) | Review isolation choices and their limitations. | Advanced; namespaces alone do not provide every required isolation boundary. |
| [Canarying releases](https://sre.google/workbook/canarying-releases/) | Review candidate evaluation, rollout design, and the limits of release signals. | Advanced; comparison quality and observation design determine whether a canary is informative. |
| [Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf) | Review compatibility and recovery concerns when versions coexist or change. | Advanced; official PDF. Application and schema compatibility must be tested in your own system. |
| [Velero documentation](https://velero.io/docs/) | Review Kubernetes backup and restore mechanisms and provider requirements. | Advanced; rehearse restore and verify application data consistency, not only object recreation. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Advanced; use documentation matching the deployed database version and test restored data. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |

## Keep telemetry, incidents, and capacity usable

Treat metrics and artifact backends as capacity consumers. Review incidents for shared impact and convert recurring platform toil into tested improvements.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus storage](https://prometheus.io/docs/prometheus/latest/storage/) | Review retention, local storage, and durability considerations for metrics infrastructure. | Advanced; public reference. Persistent storage is not a substitute for monitoring continuity or an exercised restore. |
| [Thanos documentation](https://thanos.io/tip/thanos/getting-started.md/) | Compare a distributed metrics architecture and its component responsibilities. | Advanced; public project guide. The tip documentation can describe development features; select a matching release. |
| [VictoriaMetrics documentation](https://docs.victoriametrics.com/) | Compare documented metrics ingestion, querying, deployment, and operation options. | Intermediate to advanced; public reference collection. Distinguish single-node, cluster, and commercial feature boundaries. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [The evolution of automation](https://sre.google/sre-book/automation-at-google/) | Study how automation changes operating practices and control boundaries. | Intermediate; public book chapter. Large-scale examples are design references, not a requirement to build an equivalent platform. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Cloudflare control-plane and analytics outage](https://blog.cloudflare.com/post-mortem-on-cloudflare-control-plane-and-analytics-outage/) | Compare dependency, datacenter, and recovery concerns in an original outage account. | Advanced; public historical postmortem. Distinguish affected control-plane and analytics functions from unaffected services. |

## Maintain response coordination and escalation

Review alert delivery, ownership changes, handoffs, and response roles. Test the chosen coordination path and preserve an alternative when an integration or communication service is unavailable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PagerDuty incident documentation](https://support.pagerduty.com/main/docs/incidents) | Inspect incident states, ownership, response, and notification behavior in a hosted incident platform. | Intermediate; public vendor documentation. Using the platform requires an account and suitable service access; review schedules, integrations, escalation, and feature availability. |
| [incident.io help center](https://docs.incident.io/) | Compare a hosted platform's incident response, on-call, alerting, and workflow documentation. | Intermediate; public vendor help center. Platform use requires an account and appropriate access; select direct guides and check integration and product boundaries. |
| [Being on-call](https://sre.google/sre-book/being-on-call/) | Review escalation, operating preparedness, and the human responsibilities of incident coverage. | Foundation onward; public chapter. Staffing and escalation arrangements must be agreed locally. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |

[Browse the other collections](README.md#resource-collections)

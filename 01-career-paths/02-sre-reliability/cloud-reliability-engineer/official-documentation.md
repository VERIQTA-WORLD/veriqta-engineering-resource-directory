# Cloud reliability engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [Provider foundations and workload review](#provider-foundations-and-workload-review)
- [Health, capacity, and changes](#health-capacity-and-changes)
- [Workload, telemetry, and persistent data](#workload-telemetry-and-persistent-data)
- [Provider workload signals](#provider-workload-signals)

## Provider foundations and workload review

Use the matching provider guidance to inspect actual account or project boundaries, identities, and reliability assumptions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Well-Architected reliability pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | Review reliability questions for cloud workload foundations, change, and recovery. | Intermediate; public provider framework. Review actual service limits and workload evidence; framework use is not certification. |
| [Azure Well-Architected reliability guidance](https://learn.microsoft.com/en-us/azure/well-architected/reliability/) | Find provider guidance for failure analysis, redundancy, recovery, and reliability review. | Intermediate; public framework. Apply to the deployed services and their documented responsibility boundaries. |
| [Google Cloud reliability framework](https://cloud.google.com/architecture/framework/reliability) | Review workload reliability principles and provider-specific design considerations. | Intermediate; public framework. Architecture guidance does not guarantee that every managed service meets your objective. |
| [AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/) | Explore governed multi-account foundations and service operations. | Advanced; organizational decisions, identity, networking, and account policies remain essential. |
| [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/) | Review enterprise-scale platform foundations and design areas. | Advanced; tailoring and operating ownership are required before deployment. |
| [Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations) | Review an opinionated approach to organizational cloud foundations. | Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Intermediate; validate actual permissions at the required resource scope. |

## Health, capacity, and changes

Trace provisioning failures, provider events, deployment effects, and slow recovery to the appropriate layer. Scaling is not an unlimited emergency fallback.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Health documentation](https://docs.aws.amazon.com/health/) | Find provider-event visibility and account-specific health information guidance. | Intermediate; public documentation. Provider status is one signal; it does not replace your own service measurements. |
| [Azure Service Health documentation](https://learn.microsoft.com/en-us/azure/service-health/) | Review provider incident, maintenance, and advisory visibility for Azure workloads. | Foundation onward; public reference. Access to account-specific information requires appropriate subscription permissions. |
| [Google Cloud Service Health documentation](https://cloud.google.com/service-health/docs/overview) | Find provider health and incident visibility guidance for cloud operations. | Intermediate; public reference. Compare provider events with workload telemetry and dependency evidence. |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |
| [Amazon EC2 Auto Scaling documentation](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html) | Review instance-group scaling, health, and fleet operating behavior. | Intermediate; public reference. Scaling policies need capacity, permissions, startup time, and cost review. |
| [Azure Virtual Machine Scale Sets documentation](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/) | Find fleet scaling, configuration, upgrade, and operations guidance. | Intermediate; public reference collection. Check orchestration mode and the deployed image and service versions. |
| [Google Cloud managed instance groups](https://cloud.google.com/compute/docs/instance-groups) | Review VM group management, health, and scaling guidance. | Intermediate; public reference. Regional capacity, quotas, startup time, and managed-group configuration affect outcomes. |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |

## Workload, telemetry, and persistent data

Select upstream and managed-service references for the deployed environment. A managed control plane does not own every application and storage failure.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/) | Review health-check semantics and configuration. | Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies. |
| [Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) | Review requests, limits, scheduling, and resource constraints. | Intermediate; workload measurements and node capacity are needed for useful settings. |
| [Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | Review traffic-control semantics and policy examples. | Intermediate; enforcement depends on the network implementation and its supported behavior. |
| [Kubernetes persistent volumes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) | Review storage binding, access modes, reclaim policy, and volume lifecycle. | Intermediate; public conceptual reference. Removing a claim can have data consequences depending on reclaim policy and storage implementation. |
| [Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) | Understand availability during voluntary and involuntary disruptions. | Intermediate; a disruption budget is not a universal guarantee against outages. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/) | Compare persistence modes and their durability and restart implications. | Intermediate; public guide. Persisted data and replicas are not proof of tested recovery or acceptable data loss. |

## Provider workload signals

Use these documentation entry points to find the selected provider's metrics, logs, alerting, identity, and retention guidance. Check actual service impact independently of provider status.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon CloudWatch documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) | Find AWS monitoring, alarms, logs, service signals, and collection references for workload investigation. | Intermediate; public provider documentation. An AWS account and relevant permissions are needed to operate the service; collection, retention, and features have separate billing conditions. |
| [Azure Monitor overview](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview) | Review Azure's monitoring components and links for application and infrastructure observation. | Intermediate; public provider overview. Check the selected component's data collection, identity, retention, and charging model before deployment. |
| [Google Cloud Monitoring overview](https://cloud.google.com/monitoring/docs/monitoring-overview) | Find Google Cloud metric collection, dashboards, alerting, and monitoring integration references. | Intermediate; public provider documentation. Operating access requires appropriate project permissions; telemetry volume and selected services affect charges. |

[Browse the other collections](README.md#resource-collections)

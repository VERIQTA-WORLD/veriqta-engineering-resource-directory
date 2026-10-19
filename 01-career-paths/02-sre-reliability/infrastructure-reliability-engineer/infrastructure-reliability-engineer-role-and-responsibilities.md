# Infrastructure Reliability Engineer: Role and Responsibility Resources

You need a way to repair infrastructure when the systems that normally change it are also impaired.

## Own the repair path

Map the systems needed to change infrastructure: definitions, state, identity, runners, provider APIs, and operator access. Identify which dependencies also live in the environment they must repair. Provide a supported recovery route when the normal control path fails.

## Connect resources to service outcomes

Agree workload acceptance with application and data owners. Resource creation, node readiness, workload scheduling, storage attachment, and useful requests establish different facts. Identify persistent data that must be restored rather than simply recreating empty infrastructure.

## Keep ownership and failure domains explicit

Record which controller or team owns each resource and setting. Compare failure isolation with operational complexity. Shared state, credentials, and management services can connect environments that otherwise appear separate.

## Resources behind these responsibilities

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

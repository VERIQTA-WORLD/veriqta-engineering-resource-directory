# Infrastructure Reliability Engineer: Tools and Technology Resources

Treat provisioners, schedulers, state stores, and configuration controllers as services with owners and failure paths.

## Choose coordination and state protection

Evaluate backend locking, versioning, access, and recovery for the selected tooling. Inspect capabilities rather than assuming all backends behave alike. Document how you determine whether a blocked operation is active before removing coordination.

## Treat controllers as services

Provisioners, configuration tools, schedulers, and storage controllers need credentials, upgrades, telemetry, and response ownership. Test their dependency on the managed environment. More automation can reduce toil while adding new control-plane failure paths.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| State and backend controls | Use them to track resource ownership and coordinate changes. | Recovering a state store does not restore application data or prove the environment is correct. |
| Workload resource configuration | Use it to make placement and runtime constraints explicit. | Check actual reserve capacity and dependency behavior during failure. |
| Disruption budgets | Use them within their documented scope for workload disruption. | They do not prevent every failure, create spare capacity, or replace application recovery design. |

## Implementation and diagnostic references

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).

## Reading behind the tool decision

- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

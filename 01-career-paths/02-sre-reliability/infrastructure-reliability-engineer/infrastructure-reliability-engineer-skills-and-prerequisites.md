# Infrastructure Reliability Engineer: Skills and Prerequisite Resources

Recreating resources, recovering state, restoring application data, and verifying the workload are separate skills.

## Understand control and data state

Distinguish desired configuration, infrastructure state, live resource settings, and persistent application data. They require different recovery methods. Learn how drift, interrupted changes, and missing credentials affect reconciliation.

## Reason about placement and disruption

Study scheduling, resources, replica placement, storage dependencies, and voluntary versus involuntary disruption. A workload policy cannot guarantee capacity or protect against every failure. Connect placement assumptions to the workload’s actual availability requirement.

## Read at the boundary you need to understand

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

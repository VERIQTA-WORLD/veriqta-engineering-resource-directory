# Infrastructure Reliability Engineer: Production Practice Resources

Preserve enough evidence from an interrupted change to reconcile actual resources before repeating the operation.

## Reconcile interrupted changes deliberately

Preserve change history, identify the active operation, inspect external resource state, and establish who owns recovery. Avoid repeated applies or force-unlocks without resolving uncertainty. Verify the workload after infrastructure reconciliation.

## Exercise the recovery prerequisites

Check that definitions, state, backups, identity, and execution capacity remain accessible through the intended failure scenario. Record the observed recovery sequence and act on missing dependencies. Keep cleanup aware of persistent data and shared ownership.

## Operating references

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

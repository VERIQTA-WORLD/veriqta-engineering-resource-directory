# Infrastructure Reliability Engineer: Architecture Resources

A recovery design fails early if its runner, credentials, or state store depends entirely on the environment it must repair.

## Remove circular recovery dependencies

Draw both the workload path and the repair path. If the runner, state store, or identity service fails with the workload, compare an independent recovery environment and a deliberately scoped alternate access route. Validate authority without relying on permanent unrestricted credentials.

## Separate rebuild and restoration

Classify resources as reproducible, persistent, or externally managed. Record ordering, compatible versions, and data checks. A replacement cluster may be available before its applications can use restored volumes, identities, or dependent services.

## The cluster cannot schedule its own repair

Suppose the only infrastructure runner is a workload inside the cluster being repaired. The incident also prevents that workload from reaching its state backend.

Recreating the runner inside the same failed boundary does not provide an independent repair route. Identify how an authorized operator can obtain reviewed definitions, backend access, provider credentials, and execution capacity elsewhere. Keep authority scoped to the environment and record the path’s prerequisites.

Then inspect persistent storage. Rebuilt nodes and controllers can restore compute capacity without restoring usable application data. Give infrastructure reconstruction and data restoration separate acceptance checks and owners.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

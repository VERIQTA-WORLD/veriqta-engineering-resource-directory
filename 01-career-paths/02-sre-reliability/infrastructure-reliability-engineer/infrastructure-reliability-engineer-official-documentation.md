# Infrastructure Reliability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for keeping infrastructure and its change-control dependencies operable, recoverable, and appropriately isolated. Match the installed version and actual configuration before interpreting an observation.

## Who owns this tracked resource?

Compare configuration, state identity, live settings, and external dependencies.

Read [Terraform: State](https://developer.hashicorp.com/terraform/language/state), starting with the purpose of state and its relationship to resources. State may contain sensitive values; its storage and access need explicit controls.

## Is the lock protecting active work?

Establish operation identity, executor status, backend state, and external effects.

Read [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking), starting with lock behavior and force-unlock conditions. A lock error alone does not establish that no operation is still running.

## What availability protection does the budget provide?

Match planned and unplanned events to documented behavior and spare capacity.

Read [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/), starting with voluntary and involuntary disruption and budget limits. A disruption budget does not prevent every kind of failure or guarantee spare capacity.

## Related implementation references

- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

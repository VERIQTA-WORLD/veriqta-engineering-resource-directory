# Infrastructure Reliability Engineer: Interview and Assessment Resources

These problems ask you to reason about the control path as well as the workload it manages.

## The recovery runner is inside the failed cluster

Explain which prerequisites prevent repair, which scoped alternate path is feasible, and how you would validate it. Compare authority and credential exposure with operational availability.

## Resources are recreated but the service is not restored

Trace configuration, storage, identity, networking, and application compatibility. Identify which observed boundary failed and which team owns its verification. Explain why successful provisioning cannot close the incident by itself.

## What to look for in your answer

Explain the repair prerequisites as well as the workload failure. Describe how you would recover scoped execution and state access, then verify persistent data and useful application behavior separately.

## References for checking the reasoning

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Access and technical limits](../README.md#source-state)
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking) · [Access and technical limits](../README.md#source-locking)
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) · [Access and technical limits](../README.md#source-disruption)

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Infrastructure Reliability Engineer: Learning Resources

Start with the relationship between definitions, state, and actual resources. Then study coordination, workload placement, and disruption so the repair plan covers both the control path and the service.

## Explain state ownership

Read [Terraform: State](https://developer.hashicorp.com/terraform/language/state), beginning with the purpose of state and its relationship to resources.

Map declared resources, tracked identities, actual configuration, and persistent application data.

## Understand coordination

Read [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking), beginning with lock behavior and force-unlock conditions.

Write the evidence required to distinguish active, interrupted, and abandoned operations before retry or unlock.

## Connect placement to availability

Read [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/), beginning with the resource type and scheduling/runtime behavior relevant to the workload.

Identify requested resources, node constraints, and failure reserve for one workload.

## Review disruption and recovery

Read [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/), beginning with voluntary and involuntary disruption and budget limits.

Compare a planned maintenance operation with an unexpected node failure. Specify the different checks each requires.

Choose a [project](infrastructure-reliability-engineer-labs-and-portfolio-projects.md) when you need execution evidence, or work through the [assessment scenarios](infrastructure-reliability-engineer-interview-and-assessment-resources.md) to apply the idea under changed conditions.

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

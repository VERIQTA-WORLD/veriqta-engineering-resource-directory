# Infrastructure Reliability Engineer: Labs and Portfolio Projects

## Design an independent repair path

Map how you would repair a fictional environment whose normal runner and state access are impaired.

### Set up the exercise

Begin with design-only work using synthetic infrastructure, identities, and a clearly chosen state backend.

### Investigate the behavior

Remove the main runner and one credential dependency from the model. Determine what can be recovered without bypassing ownership.

Produce dependency and authority maps, backend assumptions, operation reconciliation steps, and workload-level acceptance.

### Finish and clean up

Remove optional backend or runtime test objects only after their dedicated resources are reconciled. Revoke disposable access.

### References for this project

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Prerequisites and limitations](../README.md#source-state)
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking) · [Prerequisites and limitations](../README.md#source-locking)
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) · [Prerequisites and limitations](../README.md#source-iam)

## Compare maintenance and unexpected disruption

Inspect a small replicated workload in a disposable local cluster and examine its placement and available capacity.

### Set up the exercise

Use kind or an equivalent dedicated cluster, compatible Kubernetes tools, a synthetic workload, and a functional service check.

### Investigate the behavior

Design separate planned and unexpected disruption cases. Use the applicable upstream procedures and keep effects within the dedicated cluster.

Record requests, limits, placement, budget configuration, user outcomes, and the distinction between policy coverage and actual spare capacity.

### Finish and clean up

Remove exercise resources and the dedicated cluster using the chosen tool’s lifecycle instructions. Inspect optional storage or external integrations separately.

### References for this project

- [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) · [Prerequisites and limitations](../README.md#source-kind)
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) · [Prerequisites and limitations](../README.md#source-resources)
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) · [Prerequisites and limitations](../README.md#source-disruption)

[Back to Infrastructure Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

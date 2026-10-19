# Chaos Engineer: Labs and Portfolio Projects

## Test a dependency-failure hypothesis

Verify how a synthetic service behaves during one bounded dependency fault.

### Set up the exercise

Use a dedicated disposable Kubernetes cluster, compatible Chaos Mesh instructions, synthetic requests, a representative service check, and scoped experiment authority.

### Investigate the behavior

Choose one supported fault. Confirm the exact targets and independent stop path before injection; stop when the acceptance boundary is crossed.

Keep the hypothesis, scope, baseline, fault timeline, request outcomes, stop events, recovery checks, and an owned improvement proposal.

### Finish and clean up

End and remove the experiment, inspect residual settings and backlog, remove dedicated controllers or the cluster, and revoke temporary credentials.

### References for this project

- [Chaos Mesh documentation](https://chaos-mesh.org/docs/) · [Prerequisites and limitations](../README.md#source-chaos)
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) · [Prerequisites and limitations](../README.md#source-disruption)
- [Incident Response](https://sre.google/workbook/incident-response/) · [Prerequisites and limitations](../README.md#source-incident)

## Design a cloud fault experiment

Prepare an experiment plan for a supported AWS action without assuming that a provider tool makes the target safe.

### Set up the exercise

Design-only work needs no account. Execution requires a dedicated authorized AWS environment, current action documentation, monitoring, permissions, and a budget.

### Investigate the behavior

Assume the main monitoring path fails during disruption. Revise observation and stop controls before allowing execution.

Produce target-selection checks, authority, cost inventory, abort criteria, residual-effect checks, and application recovery acceptance.

### Finish and clean up

For any optional execution, terminate the experiment and inspect target resources, temporary access, monitoring, and ongoing charges.

### References for this project

- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html) · [Prerequisites and limitations](../README.md#source-fis)
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) · [Prerequisites and limitations](../README.md#source-aws-rel)
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/) · [Prerequisites and limitations](../README.md#source-slo)

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

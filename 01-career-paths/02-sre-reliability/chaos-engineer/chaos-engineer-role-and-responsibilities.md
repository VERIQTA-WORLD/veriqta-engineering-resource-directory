# Chaos Engineer: Role and Responsibility Resources

A fault experiment should have a hypothesis you can reject, a target you can bound, and a recovery outcome you can observe.

## Write a hypothesis that can fail

State expected useful service behavior during a specific fault and define the observation that would reject the hypothesis. “The service is resilient” is too broad. Name the dependency, affected request path, workload, exposure duration, and recovery expectation.

## Bound authority and blast radius

Identify exact targets, selectors, fault scope, executor identity, exclusions, and an independent stop path. Verify that shared dependencies will not expose unrelated users. Agreement to run one experiment is not permission to explore arbitrary failures.

## Convert observations into improvements

Separate the injected fault, observed service effect, mitigation, and recovery. Record surprises and competing explanations. Assign follow-up work to an owner and decide what evidence is required before repeating or expanding the experiment.

## Resources behind these responsibilities

- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html): Experiment concepts, targets, permissions, and stop conditions. [Access and technical limits](../README.md#source-fis).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

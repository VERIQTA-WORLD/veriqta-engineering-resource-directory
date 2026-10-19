# Chaos Engineer: Tools and Technology Resources

Choose a fault tool after choosing the assumption you need to test. Its permissions and target selectors are part of the experiment.

## Select a fault implementation

Use a tool whose documented action matches the hypothesis and environment. Review target discovery and controller permissions. Prefer a narrow local or staging experiment before introducing a more powerful shared controller.

## Separate stop controls from observations

A stop condition needs a reliable signal and a path that remains available during disruption. Test how experiment cancellation behaves. Include manual termination and operator coordination when automated protection cannot cover all consequences.

## Preserve an interpretable timeline

Connect fault activation, workload, alerts, operator actions, fault removal, and recovery observations. Keep clock and collection context. A tool reporting experiment completion establishes a different fact from restored useful service.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Chaos Mesh | Choose a supported Kubernetes fault whose scope you can isolate. | Inspect agent authority, target selectors, stop behavior, and residual effects. |
| AWS Fault Injection Service | Choose it for a supported AWS action with scoped authority and dependable stop controls. | Review the action-specific behavior and resources charged during execution. |
| Independent service observation | Use an observer that remains meaningful during the planned fault. | A vanished collector cannot report a trustworthy absence of failures. |

## Implementation and diagnostic references

- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html): Experiment concepts, targets, permissions, and stop conditions. [Access and technical limits](../README.md#source-fis).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).

## Reading behind the tool decision

- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

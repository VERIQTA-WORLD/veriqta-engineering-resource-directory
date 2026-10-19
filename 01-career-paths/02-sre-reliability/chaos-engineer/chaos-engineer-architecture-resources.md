# Chaos Engineer: Architecture Resources

The experiment design has to account for what happens when its own observation or stop path is affected.

## Map the tested dependency

Show callers, the injected boundary, shared resources, and alternate paths. Identify whether retries, failover, or queues can amplify the initial disruption. Choose a scenario that exercises an important design assumption rather than merely demonstrating a fault tool.

## Design independent containment

Ensure the experiment control and response authority do not rely entirely on the component being disrupted. Specify maximum exposure, permitted target count, and excluded resources. Review the consequences of an incorrect selector as part of the design.

## Plan an escalation sequence

Increase scope only when previous observations support doing so. Change one major assumption at a time where practical. Larger experiments need stronger evidence about shared effects, stop behavior, and operating readiness.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html): Experiment concepts, targets, permissions, and stop conditions. [Access and technical limits](../README.md#source-fis).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

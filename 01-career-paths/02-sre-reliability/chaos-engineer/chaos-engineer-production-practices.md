# Chaos Engineer: Production Practice Resources

Confirm the target and stop conditions again immediately before execution; the environment may have changed since the plan was approved.

## Run a preflight

Confirm target identity, approved scope, workload, baseline, observers, stop controls, and recovery authority immediately before execution. Check for concurrent incidents or changes that would make results hard to interpret or increase impact.

## Stop on a defined condition

Use the agreed abort criteria and preserve evidence. Avoid continuing to gather interesting observations after the safety boundary has been crossed. Track the difference between stopping the injection and recovering from its effects.

## Verify cleanup and recovery

Inspect remaining experiment objects, altered settings, resource pressure, backlogs, and application behavior. Revoke temporary authority if used. Write an improvement action that addresses the observed weakness and define a later validation.

## The stop condition must outlive the fault

Suppose you want to delay one dependency and stop if useful request failures cross the agreed threshold. Your stop alarm is collected by an agent on the same host targeted by the experiment.

The design cannot safely interpret missing telemetry as a healthy service. Move observation to an independent path, narrow the fault so collection remains dependable, or postpone execution until you have a reliable stop mechanism.

After stopping, inspect the caller backlog and reconnection behavior. Fault removal is a control event; service restoration is an application outcome. Keep both timestamps so recovery time does not end merely when the experiment tool reports completion.

## Operating references

- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html): Experiment concepts, targets, permissions, and stop conditions. [Access and technical limits](../README.md#source-fis).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

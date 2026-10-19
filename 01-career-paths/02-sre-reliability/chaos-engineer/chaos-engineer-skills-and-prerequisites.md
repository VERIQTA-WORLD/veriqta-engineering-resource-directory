# Chaos Engineer: Skills and Prerequisite Resources

Understand the injected fault and the control path before installing the machinery that can create it.

## Understand the fault mechanism

Learn what the selected action actually changes and which boundaries it can cross. Process termination, packet delay, resource pressure, and dependency denial test different assumptions. Understand controller and agent privileges before installing an experiment system.

## Build observability before disruption

Establish a stable baseline, a representative user check, and sufficient dependency signals. Confirm that the monitoring path can still report during the fault. A dashboard disappearing with the target is not enough to distinguish service failure from lost visibility.

## Know how recovery completes

Stopping injection may only remove the active fault. Reconnection, rescheduling, backlogs, stale state, and manual repairs can remain. Define recovery checks for data and user outcomes as well as infrastructure status.

## Read at the boundary you need to understand

- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/): Installation, creating a cluster, interacting with it, and deletion. [Access and technical limits](../README.md#source-kind).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

# Chaos Engineer: Official Documentation

Use the references below when you need to establish exact behavior for testing explicit resilience hypotheses through bounded, observable fault experiments. Match the installed version and actual configuration before interpreting an observation.

## Which resources can the fault action affect?

Inspect installed version, action configuration, selector results, privileges, and shared dependencies.

Read [Chaos Mesh documentation](https://chaos-mesh.org/docs/), starting with overview, installation, the chosen fault type, and lifecycle controls. Fault controllers can have substantial authority; target selection and stopping behavior need validation.

## What stops the cloud experiment?

Check target resolution, permissions, stop signals, action semantics, and independent operator control.

Read [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html), starting with experiment concepts, targets, permissions, and stop conditions. Review each action and target selector; cleanup and recovery depend on what the experiment changes.

## Which disruptions does the budget address?

Compare the fault class with the documented budget behavior and current workload state.

Read [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/), starting with voluntary and involuntary disruption and budget limits. A disruption budget does not prevent every kind of failure or guarantee spare capacity.

## Related implementation references

- [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/): Installation, creating a cluster, interacting with it, and deletion. [Access and technical limits](../README.md#source-kind).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

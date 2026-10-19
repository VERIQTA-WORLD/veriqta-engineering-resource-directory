# Resilience Engineer: Architecture Resources

A recovery plan must account for the backlog and shared dependencies left after the initial fault disappears.

## Design independent recovery prerequisites

Map the degraded service and the systems needed to restore it. Shared identity, configuration, or deployment paths can undermine a failover plan. Compare alternate authority and control routes without creating unrestricted permanent access.

## Account for data and backlog

Define how queued work, duplicate requests, stale reads, and partially completed operations behave through recovery. Plan capacity for reconnection and draining work. Returning all traffic immediately can recreate the overload that caused the failure.

## Useful degradation depends on the action

Suppose a product lookup can temporarily use older descriptive data, but an inventory reservation must prevent conflicting commitments. The same fallback is not appropriate for both actions.

Define which reads may tolerate staleness, which writes must reject or pause, and how queued work is reconciled. Add limits so retries do not exhaust the dependency while it recovers. Explain the user consequence explicitly rather than recording every fallback response as a success.

When normal operation resumes, validate data and drain deferred work within available capacity. A quick return to full traffic can recreate the initial overload even after the dependency itself has recovered.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

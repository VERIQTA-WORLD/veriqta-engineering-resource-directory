# Resilience Engineer: Role and Responsibility Resources

Decide which service remains useful during disruption and which work must stop to protect correctness.

## Define useful degraded behavior

Identify which functions must continue, which may pause, and which must reject work to protect correctness. Agree the user consequence and maximum tolerable duration. A fallback that returns plausible but incorrect data can be worse than an explicit failure.

## Contain propagation

Trace timeouts, retries, concurrency, queues, and shared-resource pressure. Identify where a dependency fault can amplify into a wider failure. Design a bounded response that preserves essential work without overwhelming the recovery target.

## Validate the recovery route

Include identity, control systems, data, staffing, and reconnection behavior. Removing the initial fault does not necessarily drain the backlog or restore consistency. Define completion using useful service and data evidence.

## Resources behind these responsibilities

- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html): Base backup prerequisites, archiving, and recovery configuration. [Access and technical limits](../README.md#source-pg-pitr).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

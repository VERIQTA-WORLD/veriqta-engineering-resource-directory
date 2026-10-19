# Resilience Engineer: Tools and Technology Resources

Different controls protect different outcomes. A fallback, a replica, and a backup should not be evaluated as interchangeable resilience features.

## Choose controls for the failure mechanism

Load shedding, isolation, concurrency limits, fallback, replication, and restoration solve different problems. Compare what they protect and what they sacrifice. Use the simplest control whose effect and operating conditions you can verify.

## Use experiments to test assumptions

Select bounded faults and representative workload in an authorized environment. Observe request outcomes, dependency pressure, and recovery. Review target scope and stop controls before choosing a fault-injection product.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Admission and load controls | Use them to protect essential work when demand exceeds useful capacity. | Decide which work can be rejected or deferred and how callers respond. |
| Fault experiments | Use them to test a defined degradation or recovery assumption. | Target scope and stopping need validation before adding disruption. |
| Replication and restore mechanisms | Use each for the failure class it addresses. | Replicating corruption and restoring a usable historical state are different concerns. |

## Implementation and diagnostic references

- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html): Base backup prerequisites, archiving, and recovery configuration. [Access and technical limits](../README.md#source-pg-pitr).

## Reading behind the tool decision

- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

# Resilience Engineer: Skills and Prerequisite Resources

Slow dependencies, ambiguous completion, retries, and queues can turn a small disruption into a wider failure.

## Understand dependency failure behavior

Study how callers behave when a dependency is slow, unavailable, or returns ambiguous results. Distinguish transient failure from overload and partial completion. Retrying a request may amplify load or duplicate an external effect.

## Separate availability and recoverability

Redundancy can support continued operation, while restoration handles different loss or corruption scenarios. Learn the ordering and authority required to recover. Evaluate the service while degraded and after return to normal, not only the initial failover.

## Read at the boundary you need to understand

- [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/): Request handling, dependencies, and the relevant operating concern. [Access and technical limits](../README.md#source-service).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html): Base backup prerequisites, archiving, and recovery configuration. [Access and technical limits](../README.md#source-pg-pitr).
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/): Voluntary and involuntary disruption and budget limits. [Access and technical limits](../README.md#source-disruption).

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

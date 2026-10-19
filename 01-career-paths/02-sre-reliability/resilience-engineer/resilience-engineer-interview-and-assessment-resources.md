# Resilience Engineer: Interview and Assessment Resources

Explain what useful service means under degraded conditions before choosing a fallback or a return-to-normal action.

## Fallback preserves availability but changes results

Explain which user actions can tolerate degraded data and which require correctness. Compare explicit rejection, reduced functionality, and a fallback using the actual requirement rather than maximizing a superficial success rate.

## Traffic returns and the service fails again

Investigate backlog, cache state, reconnection, retry amplification, and recovery capacity. Propose staged acceptance with observations that justify each step and clear conditions for stopping.

## What to look for in your answer

Explain the user and data consequences of degradation. Include the backlog, reconnection behavior, and capacity required to return to normal without recreating the failure.

## References for checking the reasoning

- [Chaos Mesh documentation](https://chaos-mesh.org/docs/) · [Access and technical limits](../README.md#source-chaos)
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) · [Access and technical limits](../README.md#source-disruption)
- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) · [Access and technical limits](../README.md#source-pg-pitr)
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/) · [Access and technical limits](../README.md#source-cascade)
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/) · [Access and technical limits](../README.md#source-overload)

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

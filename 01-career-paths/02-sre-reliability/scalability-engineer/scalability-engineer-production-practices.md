# Scalability Engineer: Production Practice Resources

Watch the gain in useful work from the next unit of capacity; a change in that gain is a reason to investigate the next limit.

## Watch useful throughput per resource

Compare completed user work with resource usage and errors as demand grows. Inspect whether additional replicas add useful capacity or just connections and coordination. Investigate the point where the marginal gain changes.

## Repeat validation after meaningful change

Reassess after large changes to data volume, tenant mix, request behavior, or dependencies. Preserve the workload definition and baseline for comparison. Set stop conditions so a test cannot overwhelm a shared downstream service.

## Operating references

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/): Metrics, control behavior, readiness, and stabilization. [Access and technical limits](../README.md#source-hpa).
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html): Connection settings and their resource implications. [Access and technical limits](../README.md#source-pg-conn).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

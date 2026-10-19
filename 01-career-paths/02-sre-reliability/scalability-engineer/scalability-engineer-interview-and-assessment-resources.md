# Scalability Engineer: Interview and Assessment Resources

These scenarios require an explanation of the bottleneck before another scaling action.

## Doubling replicas does not improve throughput

Compare generator limits, shared database pressure, serialized work, network constraints, and contention. State which observation would identify the bottleneck before choosing another scaling action.

## One tenant dominates a partition

Explain how you would distinguish request volume, key distribution, expensive operations, and data-size skew. Compare limiting demand, isolating the tenant, and repartitioning, including migration and correctness costs.

## What to look for in your answer

Explain why additional resources would relieve the limiting work. Keep key distribution, shared dependencies, generator limits, and useful throughput visible in the comparison.

## References for checking the reasoning

- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/) · [Access and technical limits](../README.md#source-k6)
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/) · [Access and technical limits](../README.md#source-hpa)
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html) · [Access and technical limits](../README.md#source-pg-conn)
- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/) · [Access and technical limits](../README.md#source-nasd)

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

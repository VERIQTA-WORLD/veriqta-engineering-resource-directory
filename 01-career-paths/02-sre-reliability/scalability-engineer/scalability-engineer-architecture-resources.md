# Scalability Engineer: Architecture Resources

Compare scaling strategies using the observed bottleneck, key distribution, consistency needs, and migration cost.

## Compare scale-up and scale-out

Evaluate useful throughput, failure impact, deployment limits, coordination overhead, and cost. Horizontal scaling may be constrained by shared state or serialized work. A larger instance can be an appropriate intermediate step when it addresses the measured limit.

## Design partitioning with ownership

Choose keys and boundaries using access patterns, data locality, tenant skew, and consistency requirements. Include rebalancing and migration. A partitioning design that works only with uniform traffic needs a plan for the hot partition.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/): Metrics, control behavior, readiness, and stabilization. [Access and technical limits](../README.md#source-hpa).
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html): Connection settings and their resource implications. [Access and technical limits](../README.md#source-pg-conn).

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

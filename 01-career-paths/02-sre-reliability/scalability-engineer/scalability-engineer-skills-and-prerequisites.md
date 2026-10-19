# Scalability Engineer: Skills and Prerequisite Resources

Follow the work created by a user operation, including internal calls, queries, retries, and coordination.

## Understand work amplification

Trace how one user operation becomes internal calls, queries, retries, and storage work. Measure where growth multiplies coordination or data movement. A throughput estimate based only on the frontend can miss the dependency doing most of the work.

## Learn workload-sensitive measurement

Use comparable data size, request distribution, arrival model, and service objectives. Inspect errors and tail behavior. A benchmark on cached data with balanced keys may not predict production behavior under skew or a larger working set.

## Read at the boundary you need to understand

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/): Metrics, control behavior, readiness, and stabilization. [Access and technical limits](../README.md#source-hpa).
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html): Connection settings and their resource implications. [Access and technical limits](../README.md#source-pg-conn).

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

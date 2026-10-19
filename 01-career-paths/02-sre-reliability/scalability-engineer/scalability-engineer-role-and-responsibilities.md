# Scalability Engineer: Role and Responsibility Resources

Your task is to explain why useful throughput changes as demand, data, and resource counts grow.

## Explain the next growth limit

Characterize workload size, request mix, data distribution, concurrency, and useful completion. Identify the current bottleneck and how it changes with growth. Scaling is a system behavior question, not simply a count of replicas or machines.

## Test the mechanism of improvement

Compare partitioning, resource changes, concurrency control, caching, and reduced work per request. State why a proposed action should relieve the observed limit. Validate the entire service because a local gain may shift pressure elsewhere.

## Plan skew and coordination

Consider uneven tenants, hot keys, shared locks, synchronization, and data movement. Balanced averages can hide one overloaded partition. Include redistribution, migration, and operating costs in the design.

## Resources behind these responsibilities

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/): Metrics, control behavior, readiness, and stabilization. [Access and technical limits](../README.md#source-hpa).
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html): Connection settings and their resource implications. [Access and technical limits](../README.md#source-pg-conn).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

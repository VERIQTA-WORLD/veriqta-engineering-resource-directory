# Capacity Engineer: Skills and Prerequisite Resources

Throughput, concurrency, queue delay, and resource utilization answer different questions. Learn how their measurement boundaries relate.

## Read distributions and time windows

Learn to interpret throughput, concurrent work, queue delay, service time, and latency percentiles over comparable intervals. Keep the offered workload visible. Averages across hosts or tenants can hide imbalance and tail behavior that matters to users.

## Distinguish a model from a measurement

Use arithmetic to estimate resource needs, then validate the assumptions with an appropriate workload. Relationships between concurrency, throughput, and time require compatible boundaries and sufficiently stable intervals. A growing queue violates the steady-state assumptions behind many simple estimates.

## Understand resource enforcement

Study how CPU, memory, storage, and connection controls behave in the actual runtime. Account for reservations, limits, and scheduling constraints. A resource setting can influence placement or termination without guaranteeing that the application meets a latency objective.

## Read at the boundary you need to understand

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

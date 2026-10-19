# Capacity Engineer: Official Documentation

Use the references below when you need to establish exact behavior for matching usable resources to current and forecast demand under performance and failure constraints. Match the installed version and actual configuration before interpreting an observation.

## What capacity is requested, limited, or actually available?

Compare workload configuration with placement and runtime observations.

Read [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/), starting with the resource type and scheduling/runtime behavior relevant to the workload. CPU and memory controls have different effects; a scheduling request is not a complete capacity model.

## When do new replicas become useful?

Record metric availability, scaling decisions, scheduling, startup, readiness, and dependency limits.

Read [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/), starting with metrics, control behavior, readiness, and stabilization. Replica changes require downstream capacity and time to become useful; limits and dependencies still matter.

## Did the test offer the intended workload?

Inspect achieved demand, generator resources, request mix, errors, and useful completions.

Read [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/), starting with the test type matching your question, then its workload model. A load generator can become the bottleneck; validate the offered workload as well as the target.

## Related implementation references

- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

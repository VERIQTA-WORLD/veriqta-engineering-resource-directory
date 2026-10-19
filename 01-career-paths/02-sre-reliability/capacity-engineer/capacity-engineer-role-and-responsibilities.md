# Capacity Engineer: Role and Responsibility Resources

A capacity decision needs to say how much useful work the service can sustain, under which workload, and with what failure reserve.

## Model demand in useful units

Choose demand units that connect to user work: successful requests, jobs, active sessions, or data processed. Separate offered demand from accepted and completed work. Include bursts, request mix, retries, and background tasks; a daily average can conceal the period that determines the capacity requirement.

## Define usable headroom

Headroom depends on the performance objective and failure assumptions. Measure the point at which useful throughput stops increasing or latency becomes unacceptable. Compare normal and degraded capacity. Spare CPU does not establish spare capacity when connections, storage, locks, or a dependency constrain completion.

## Own a decision rather than an estimate

Present a forecast range, its assumptions, the lead time for adding resources, and a trigger for acting. Compare reserving capacity, improving efficiency, managing demand, and changing the architecture. Revisit estimates when workload behavior or the service objective changes.

## Resources behind these responsibilities

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/): Metrics, control behavior, readiness, and stabilization. [Access and technical limits](../README.md#source-hpa).
- [FinOps Framework](https://www.finops.org/framework/): Scope, allocation, ownership, and improvement capabilities. [Access and technical limits](../README.md#source-finops).

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

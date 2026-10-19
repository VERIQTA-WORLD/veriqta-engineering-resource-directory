# Scalability Engineer: Tools and Technology Resources

More replicas are not necessarily more capacity when the added callers share a constrained database or serialized path.

## Validate the load generator

Measure achieved arrival rate and generator saturation. Choose test duration and workload shape according to the question. Include error handling so a failing response does not look like fast useful work.

## Use scaling controls within their envelope

Autoscaling changes capacity only after metrics, decisions, provisioning, and readiness. Confirm downstream quotas and connection limits. Consider admission control or architectural changes when the limiting resource cannot scale at the same rate.

## More replicas can move pressure into the database

Suppose each application replica opens a pool of 20 database connections. Moving from five replicas to ten changes the configured pool capacity from 100 to 200 connections, assuming every pool reaches that size.

That arithmetic does not establish 200 simultaneous useful transactions or twice the throughput. Inspect actual connection use, transaction duration, waits, memory, and database completions. The extra replicas may relieve application CPU while increasing contention or retry pressure downstream.

Compare smaller pools, admission control, query changes, and additional database capacity against the observed bottleneck. Keep the workload and correctness requirement constant when evaluating whether the next scaling action helps.

Read [k6’s open and closed workload models](https://grafana.com/docs/k6/latest/using-k6/scenarios/concepts/open-vs-closed/) when deciding how the generator should offer work. The arrival model affects what a slowdown in the target does to generated demand.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Workload generator | Use it to compare useful throughput under a defined request and data distribution. | Keep generator limits, rejected work, errors, and tail latency visible. |
| Replica autoscaling | Use it when parallel work and downstream resources can benefit from more replicas. | Shared locks, hot partitions, and connection pressure can prevent proportional improvement. |
| Connection configuration | Use it alongside application concurrency and pooling behavior. | The configured connection count is not a throughput guarantee. |

## Implementation and diagnostic references

- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/): Metrics, control behavior, readiness, and stabilization. [Access and technical limits](../README.md#source-hpa).
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html): Connection settings and their resource implications. [Access and technical limits](../README.md#source-pg-conn).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).

## Reading behind the tool decision

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

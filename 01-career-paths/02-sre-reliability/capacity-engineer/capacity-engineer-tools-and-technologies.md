# Capacity Engineer: Tools and Technology Resources

A load test can look successful because the generator stopped offering enough work. Validate the workload before trusting the target measurements.

## Choose workload generation deliberately

Select a load model that represents arrival behavior, request diversity, and data size. Validate generator capacity and the achieved workload. A test that slows its own request generation as the target degrades can conceal demand that the service would face in production.

## Connect metrics to saturation

Collect queue depth and age, useful completions, errors, resource pressure, and relevant dependency behavior. Inspect the limiting resource rather than adding dashboards indiscriminately. Retain comparable intervals before, during, and after a change.

## Use scaling as one option

Autoscaling can add resources after a measured trigger, but useful capacity arrives only after scheduling, startup, readiness, and dependency access. Account for quotas and downstream limits. Compare predictive provisioning or demand control when response time is too slow.

Read [k6’s open and closed workload models](https://grafana.com/docs/k6/latest/using-k6/scenarios/concepts/open-vs-closed/) when deciding how the generator should offer work. The arrival model affects what a slowdown in the target does to generated demand.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| k6 workload tests | Use a workload shape that addresses peak, endurance, or another specific capacity question. | Observe the generator as well as the target; check offered demand and useful completions. |
| Kubernetes resource controls | Use requests and limits to express the scheduling and runtime constraints you intend. | Placement, throttling, termination, and application performance are different effects. |
| Horizontal autoscaling | Use it when a suitable metric can trigger capacity in time. | Include startup delay, pending replicas, quotas, and downstream limits. |

## Implementation and diagnostic references

- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/): Metrics, control behavior, readiness, and stabilization. [Access and technical limits](../README.md#source-hpa).

## Reading behind the tool decision

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [FinOps Framework](https://www.finops.org/framework/): Scope, allocation, ownership, and improvement capabilities. [Access and technical limits](../README.md#source-finops).

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

# Capacity Engineer: Learning Resources

Define useful demand first, then choose a workload model. Resource and scaling controls make more sense once you can identify the capacity question they must answer.

## Describe the workload

Read [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/), beginning with requirements, estimates, component capacity, and failure assumptions.

Write demand units, request mix, peak intervals, data growth, and failure assumptions. Distinguish known measurements from estimates.

## Choose a representative experiment

Read [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/), beginning with the test type matching your question, then its workload model.

Specify arrival behavior, request classes, test duration, generator observations, and service acceptance. Explain what would make the experiment unrepresentative.

## Identify overload and usable headroom

Read [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/), beginning with load shedding, request handling, and overload controls.

Compare useful completions, queue behavior, errors, and tail latency. Mark the range in which the objective is met.

## Evaluate a capacity action

Read [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/), beginning with the resource type and scheduling/runtime behavior relevant to the workload.

Connect the runtime resource controls to placement and application behavior. Compare added capacity with demand management and retained failure reserve.

Choose a [project](capacity-engineer-labs-and-portfolio-projects.md) when you need execution evidence, or work through the [assessment scenarios](capacity-engineer-interview-and-assessment-resources.md) to apply the idea under changed conditions.

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

# Capacity Engineer: Production Practice Resources

Low average CPU does not close a capacity investigation when users are waiting and queues are growing.

## Validate the offered workload

Inspect actual arrivals, accepted work, dropped work, completions, retries, and errors. Confirm that test or production traffic represents the forecast question. A high completion rate is misleading if the system rejects most demand before it reaches the measurement boundary.

## Review peak and failure reserve together

Track the busiest relevant intervals and degraded-state requirements. Investigate which resource limits useful work first. Schedule new validation after substantial code, configuration, data-size, or dependency changes because earlier capacity evidence may no longer apply.

## Turn findings into an owned action

Record the next constraint, trigger, owner, cost, and implementation lead time. Verify that the action improves the intended service outcome. Capacity reports should lead to decisions; an estimate without an action boundary leaves the team exposed to predictable growth.

## Operating references

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

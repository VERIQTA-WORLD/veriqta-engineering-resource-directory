# Capacity Engineer: Architecture Resources

Capacity architecture begins with the workload you still need to serve after the failure you intend to tolerate.

## Design for a degraded capacity envelope

Calculate the workload the system can serve after losing the failure domain you intend to tolerate. Include uneven placement and shared dependencies. Decide whether to retain spare capacity, shed lower-priority work, or reduce functionality; document the user consequence of each option.

## Make bottleneck movement explicit

Increasing application capacity can move pressure to storage or a database. Model the entire request path and the work amplification at each stage. Compare end-to-end throughput after a change rather than interpreting the added resource count as the outcome.

## Include acquisition and operating lead time

Capacity decisions depend on procurement, quota approval, data movement, warm-up, and staff capacity. Set action thresholds early enough to accommodate those delays. Include cost ownership and a plan for removing surplus capacity without undermining the failure reserve.

## Headroom after a zone loss

Assume a measured workload can sustain 600 useful requests per second in each of three zones while meeting its latency requirement. Assume normal demand peaks at 1,000 requests per second and that the workload is evenly distributable. These values are a design example.

Normal capacity is 1,800 requests per second. After losing one zone, the remaining measured capacity is 1,200. The apparent 800-request normal reserve becomes 200 requests per second under the failure assumption: about 16.7% of the remaining capacity.

Now challenge the assumptions. Shared database pressure, uneven placement, a different request mix, or slow traffic redistribution could invalidate the sum. Treat the arithmetic as a model to validate, not a substitute for degraded-state evidence. Define when new capacity must be ready and what lower-priority demand can be limited if the margin disappears.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/): Requirements, estimates, component capacity, and failure assumptions. [Access and technical limits](../README.md#source-nasd).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/): The test type matching your question, then its workload model. [Access and technical limits](../README.md#source-k6).
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/): The resource type and scheduling/runtime behavior relevant to the workload. [Access and technical limits](../README.md#source-resources).

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

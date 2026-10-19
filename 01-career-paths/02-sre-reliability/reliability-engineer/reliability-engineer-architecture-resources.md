# Reliability Engineer: Architecture Resources

Translate reliability goals into scenarios with workload, failure, data, and recovery requirements.

## Translate objectives into scenarios

Describe the workload, fault, required useful behavior, data constraint, and recovery expectation. Compare design options against the same scenario. Avoid assigning an availability target without connecting it to dependencies and operating capacity.

## Inspect common-mode failure

Redundant components may share identity, configuration, data, power, network, or control systems. Identify correlated paths rather than multiplying optimistic component availability figures. Record assumptions that require measurement or specialist review.

## An aggregate objective can hide the important failure

Suppose a service records 99.9% success across all requests, while a small group of users cannot complete a high-value transaction. The aggregate can be numerically correct and still be insufficient for the requirement.

Identify eligible events, the affected user group, the failed journey, and the business consequence. Decide whether separate indicators or objectives are needed. Do not simply remove the failing events or invent a target after seeing the result.

Compare the intervention against the actual user outcome. A component dashboard might help locate the fault, but it cannot define success for the transaction on its own.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/): Request handling, dependencies, and the relevant operating concern. [Access and technical limits](../README.md#source-service).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).

[Back to Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

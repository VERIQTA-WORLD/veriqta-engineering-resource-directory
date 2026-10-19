# Reliability Engineer: Tools and Technology Resources

Select instrumentation and controls to resolve a reliability question rather than to complete a standard tool inventory.

## Start with a question

Choose instrumentation, dashboards, alerts, and experiments to resolve a specific uncertainty. More data can increase cost and interpretation effort without improving decisions. Keep the service outcome and operating owner visible in tool selection.

## Compare prevention and recovery controls

Testing, isolation, load management, release controls, and restore capabilities address different risks. Evaluate coverage and maintenance. A control useful for one failure class can leave another unchanged or introduce a new dependency.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| User-level indicators | Use them to measure the behavior the requirement actually names. | Inspect event eligibility and important user populations before trusting an aggregate. |
| Alert-rule tests | Use synthetic series to check evaluation behavior. | They do not validate instrumentation, scraping, notification delivery, or operator response. |
| Decision records | Use them to compare interventions and retain the reason for a choice. | A written decision still needs an owner and evidence that the control has the intended effect. |

## Reading behind the tool decision

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/): Request handling, dependencies, and the relevant operating concern. [Access and technical limits](../README.md#source-service).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).
- [FinOps Framework](https://www.finops.org/framework/): Scope, allocation, ownership, and improvement capabilities. [Access and technical limits](../README.md#source-finops).

[Back to Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

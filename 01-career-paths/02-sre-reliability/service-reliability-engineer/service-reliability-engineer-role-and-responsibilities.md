# Service Reliability Engineer: Role and Responsibility Resources

Define service health through the user journey and the dependencies required to complete it.

## Define the service through user journeys

Identify the request or completed task that matters, the eligible population, and the measurement window. Include dependencies necessary for useful success. A health endpoint can establish process responsiveness without verifying a purchase, login, or completed job.

## Connect ownership to response

Document service boundaries, dependency owners, release authority, and escalation. Define what the team can mitigate directly and what requires coordination. A dependency objective does not automatically guarantee the end-to-end user outcome.

## Use objectives in change decisions

Agree how service-level evidence influences releases, capacity, and improvement work. Track the reason behind a decision when objectives conflict with product needs. Targets are useful when they change behavior and expose risk clearly.

## Resources behind these responsibilities

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/): Request handling, dependencies, and the relevant operating concern. [Access and technical limits](../README.md#source-service).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Service Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

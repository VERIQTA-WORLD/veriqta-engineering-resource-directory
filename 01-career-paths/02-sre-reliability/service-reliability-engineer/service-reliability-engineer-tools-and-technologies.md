# Service Reliability Engineer: Tools and Technology Resources

Metrics, traces, functional checks, and alerts contribute different evidence to service reliability.

## Choose signals around the journey

Combine functional checks, request outcomes, logs, metrics, and traces according to the service question. Track data quality and sampling. A trace can help explain a path while a complete event counter may be more appropriate for an objective denominator.

## Connect alerts to an action

Use objective-based alerts and runbooks that reflect user impact and response urgency. Test rules with synthetic series and validate notification paths separately. An alert without ownership or an appropriate response adds interruption without improving reliability.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Event-based indicators | Use them when you can classify meaningful eligible and successful operations. | Define missing-data and low-traffic behavior rather than silently treating gaps as success. |
| Metrics, traces, and functional checks | Use each for measurement or diagnosis at the relevant boundary. | A sampled trace and a complete event counter support different conclusions. |
| Release comparison | Use it to compare affected behavior under relevant exposure. | Too little traffic or the wrong request mix can leave the change unevaluated. |

## Implementation and diagnostic references

- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).

## Reading behind the tool decision

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/): Request handling, dependencies, and the relevant operating concern. [Access and technical limits](../README.md#source-service).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Service Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

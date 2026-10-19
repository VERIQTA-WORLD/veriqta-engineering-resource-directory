# Service Reliability Engineer: Architecture Resources

The service boundary used for its objective must match the request path and dependencies being designed.

## Define the service boundary

Show clients, gateways, application components, data stores, and external dependencies needed for useful completion. Identify which request classes can degrade independently. Avoid a service objective whose scope differs from the architecture being reviewed.

## Design acceptance and recovery together

Specify the baseline, relevant signals, release exposure, stop conditions, and recovery checks. Include data compatibility and side effects. A rollback that restores a previous image may not restore the original behavior after a dependency or schema change.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).

[Back to Service Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

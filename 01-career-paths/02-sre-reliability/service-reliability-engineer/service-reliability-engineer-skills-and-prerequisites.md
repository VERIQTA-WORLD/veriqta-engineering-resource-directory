# Service Reliability Engineer: Skills and Prerequisite Resources

An indicator needs a clear population, event classification, time window, and treatment of missing observations.

## Build indicators carefully

Learn event-based and time-based measurement, successful versus eligible events, windows, and request classes. Decide how missing data and low traffic are handled. Keep materially different user journeys separate when one aggregate would hide a harmful failure.

## Trace dependencies and release effects

Connect artifact, configuration, data, and dependency changes to user-visible observations. Understand what readiness and health checks cover. Learn to compare affected and unaffected users without assuming a healthy component means a healthy service.

## Read at the boundary you need to understand

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/): Test file format, input series, and expected rule results. [Access and technical limits](../README.md#source-rules).

[Back to Service Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Service Reliability Engineer: Labs and Portfolio Projects

## Define and test a user-level objective

Create synthetic service events for a checkout-like journey with success, dependency failure, and missing data.

### Set up the exercise

Use a small local dataset and a clearly defined indicator. Rule testing requires compatible Prometheus tooling and synthetic series.

### Investigate the behavior

Compare the real journey with a health endpoint that omits a dependency. Explain the difference in measured success.

Keep event definitions, eligible population, windows, query or rule logic, boundary cases, and expected results.

### Finish and clean up

Remove local test artifacts and any optional dedicated monitoring services. Keep no real customer events in published examples.

### References for this project

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/) · [Prerequisites and limitations](../README.md#source-slo)
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) · [Prerequisites and limitations](../README.md#source-burn)
- [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/) · [Prerequisites and limitations](../README.md#source-rules)

## Evaluate release acceptance

Design a canary decision for a dependency-changing release.

### Set up the exercise

Use a fictional service or an owned synthetic application with known acceptance checks. Runtime work needs a bounded environment and a stop plan.

### Investigate the behavior

Give the canary too little relevant traffic, then define an appropriate additional validation route rather than declaring the absence of errors conclusive.

Produce baseline, exposure assumptions, comparison signals, data-compatibility questions, stop conditions, and recovery verification.

### Finish and clean up

Remove optional release resources and restore lab configuration. Label predicted outcomes separately from actual observations.

### References for this project

- [Canarying Releases](https://sre.google/workbook/canarying-releases/) · [Prerequisites and limitations](../README.md#source-canary)
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/) · [Prerequisites and limitations](../README.md#source-otel)
- [Incident Response](https://sre.google/workbook/incident-response/) · [Prerequisites and limitations](../README.md#source-incident)

[Back to Service Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Reliability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for turning user and business requirements into measurable reliability decisions across a system lifecycle. Match the installed version and actual configuration before interpreting an observation.

## Does the chosen indicator match the user outcome?

Inspect event eligibility, classification, windows, missing data, and important request classes.

Read [Implementing SLOs](https://sre.google/workbook/implementing-slos/), starting with selecting indicators, targets, and the improvement process. Targets require product and operational judgment; example values are not universal requirements.

## Does the alert evaluate as intended?

Use synthetic series to test the documented rule behavior and evaluate delivery separately.

Read [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/), starting with test file format, input series, and expected rule results. Synthetic series tests do not establish that instrumentation, scraping, or notification delivery works end to end.

## Does the observed signal explain the boundary?

Check instrumentation scope, sampling, collection, identity, and correlation context.

Read [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/), starting with signals relevant to your diagnostic question. Instrumentation does not automatically supply storage, retention, or an actionable alert.

[Back to Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

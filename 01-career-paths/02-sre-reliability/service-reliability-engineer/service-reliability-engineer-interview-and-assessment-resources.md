# Service Reliability Engineer: Interview and Assessment Resources

Practise finding the gap between what the service reports and what users can actually accomplish.

## Availability looks high while checkout fails

Identify the measurement boundary and missing dependency coverage. Define an indicator for useful checkout completion and explain which user groups or failures the existing measure excluded.

## A canary has no failing requests

Ask whether the canary received enough relevant traffic and exercised the changed path. Explain how low exposure, caching, or request mix limits the conclusion and what additional evidence would support proceeding.

## What to look for in your answer

Check whether the indicator and release exposure cover the affected journey. Distinguish a lack of relevant observations from evidence that the change is safe to expand.

## References for checking the reasoning

- [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/) · [Access and technical limits](../README.md#source-rules)
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/) · [Access and technical limits](../README.md#source-otel)
- [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) · [Access and technical limits](../README.md#source-debug)
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/) · [Access and technical limits](../README.md#source-slo)
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) · [Access and technical limits](../README.md#source-burn)

[Back to Service Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

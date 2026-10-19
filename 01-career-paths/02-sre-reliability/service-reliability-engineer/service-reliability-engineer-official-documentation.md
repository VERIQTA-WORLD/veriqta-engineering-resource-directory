# Service Reliability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for connecting service ownership, user journeys, objectives, dependencies, releases, and recovery. Match the installed version and actual configuration before interpreting an observation.

## Does the alert rule handle boundary cases?

Test synthetic success, failure, sparse traffic, missing data, and evaluation transitions.

Read [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/), starting with test file format, input series, and expected rule results. Synthetic series tests do not establish that instrumentation, scraping, or notification delivery works end to end.

## Which signal captures useful success?

Inspect the actual instrumentation boundary and collection behavior before choosing the denominator.

Read [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/), starting with signals relevant to your diagnostic question. Instrumentation does not automatically supply storage, retention, or an actionable alert.

## What does the application status establish?

Compare platform observations with the service path and dependency behavior.

Read [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/), starting with the guide matching the failing application boundary. A symptom requires local evidence; a diagnostic catalog does not establish its cause.

[Back to Service Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Site Reliability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for applying software engineering to service reliability, operational workload, release safety, and incident learning. Match the installed version and actual configuration before interpreting an observation.

## What does the alert test prove?

Separate rule evaluation from real instrumentation, scraping, routing, and human response.

Read [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/), starting with test file format, input series, and expected rule results. Synthetic series tests do not establish that instrumentation, scraping, or notification delivery works end to end.

## What runtime failure can you observe?

Match the diagnostic procedure to the workload and record the hypothesis each check addresses.

Read [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/), starting with the guide matching the failing application boundary. A symptom requires local evidence; a diagnostic catalog does not establish its cause.

## What side effects can automation create?

Inspect arguments, process status, timeouts, output, credentials, and work that may continue externally.

Read [Python subprocess reference](https://docs.python.org/3/library/subprocess.html), starting with frequently used arguments and security considerations. Shell interpretation and process side effects need deliberate control; select your Python version.

[Back to Site Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

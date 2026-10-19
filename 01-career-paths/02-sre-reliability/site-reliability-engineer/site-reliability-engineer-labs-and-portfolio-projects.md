# Site Reliability Engineer: Labs and Portfolio Projects

## Engineer away a recurring interruption

Choose a synthetic or sanitized recurring operational task and compare simplifying, automating, redesigning, or retiring it.

### Set up the exercise

Begin with a task record and ownership map. Implement only against owned disposable targets with bounded permissions.

### Investigate the behavior

Include invalid input, a dependency outage, and an interrupted response in the proposed test set.

Keep the baseline effort, expected mechanism, operation contract, failure evidence, maintenance estimate, and acceptance decision.

### Finish and clean up

Remove temporary execution access and resources. Preserve code and sanitized observations without active credentials.

### References for this project

- [Google SRE: Eliminating Toil](https://sre.google/sre-book/eliminating-toil/) · [Prerequisites and limitations](../README.md#source-toil)
- [Python subprocess reference](https://docs.python.org/3/library/subprocess.html) · [Prerequisites and limitations](../README.md#source-python)
- [Incident Response](https://sre.google/workbook/incident-response/) · [Prerequisites and limitations](../README.md#source-incident)

## Connect an objective to actionable response

Build a synthetic objective and alert-rule test set, then write an operator response and improvement plan.

### Set up the exercise

Use compatible Prometheus tooling, synthetic series, a defined service journey, and no real paging recipients.

### Investigate the behavior

Test steady success, sustained failure, short spikes, low traffic, and missing observations. Separate rule behavior from end-to-end notification testing.

Keep indicator and window definitions, expected evaluations, actual test results, response steps, and a proposed long-term improvement.

### Finish and clean up

Remove test rules from any retained environment and ensure that no live notifications or scheduled jobs remain active.

### References for this project

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/) · [Prerequisites and limitations](../README.md#source-slo)
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) · [Prerequisites and limitations](../README.md#source-burn)
- [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/) · [Prerequisites and limitations](../README.md#source-rules)

[Back to Site Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Site Reliability Engineer: Skills and Prerequisite Resources

A useful on-call investigation depends on a model of processes, requests, state, dependencies, and observations.

## Develop broad diagnostic literacy

Understand processes, networking, application dependencies, state, and telemetry sufficiently to choose the next useful observation. Go deeper where the service needs it. A memorized command set cannot replace a model of why an observation matters.

## Learn software and operating design

Practise writing maintainable automation, testing failure paths, and defining interfaces. Understand how software changes affect deployment, data, capacity, and response. Keep the operating owner and recovery path visible when introducing automation.

## Read at the boundary you need to understand

- [Google SRE: Eliminating Toil](https://sre.google/sre-book/eliminating-toil/): Characteristics of toil and how to identify repeated operational effort. [Access and technical limits](../README.md#source-toil).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).
- [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/): Test file format, input series, and expected rule results. [Access and technical limits](../README.md#source-rules).
- [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/): The guide matching the failing application boundary. [Access and technical limits](../README.md#source-debug).

[Back to Site Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

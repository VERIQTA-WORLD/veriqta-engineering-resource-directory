# Service Reliability Engineer: Production Practice Resources

A release should be accepted using evidence from the affected journey, including when traffic is too sparse to be conclusive.

## Inspect objective data quality

Check event eligibility, classification, collection gaps, and important subpopulations. Compare the reported indicator with functional user observations. Investigate inconsistent results before changing the target or declaring success.

## Make release evidence meaningful

Measure the affected journey through representative traffic and dependency use. Record uncertainty when traffic is sparse. After mitigation, verify useful completion and remaining side effects, then improve the check that missed the problem.

## No observed canary errors is not the same as relevant exposure

Suppose a canary receives 100 requests, but none exercises the payment path changed by the release. The absence of errors says little about the change you need to evaluate.

Inspect request mix, affected users, dependency behavior, and baseline comparability. Choose an additional authorized check that exercises the relevant path, or wait for enough appropriate exposure. Do not silently treat low traffic as strong evidence.

Before increasing exposure, confirm data compatibility and the stop and recovery conditions. Keep the release decision tied to the changed user journey rather than the simplest available success counter.

## Operating references

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Service Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

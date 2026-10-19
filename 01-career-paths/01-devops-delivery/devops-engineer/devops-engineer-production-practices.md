# DevOps Engineer: Production Practice Resources

A green pipeline can coexist with a broken checkout. Release evidence has to reach beyond the workflow that performed the deployment.

## Define acceptance before deployment

Choose functional checks and service signals that represent the affected user journey. Establish the baseline, observation period, and stop conditions. Low traffic may provide too little evidence for a confident release decision; identify another appropriate validation route.

## Investigate across boundaries

Compare timing, affected users, request paths, configuration, dependencies, and artifact identity. Preserve evidence before making unrelated changes. If reducing impact requires mitigation, record what it changed and what remains unknown about the cause.

## Verify recovery and learn

Confirm the intended user outcome after mitigation and inspect persistent side effects. Update the test or runbook that would have reduced uncertainty. Avoid turning a single incident's fix into a universal action for every similar-looking symptom.

## Checkout fails while the health endpoint succeeds

Suppose the new image starts and `/health` returns success, but checkout fails when it calls the database. The release changed a connection setting and introduced code expecting a new schema.

| Observation | Next question |
| --- | --- |
| Only the new version fails | Which artifact, configuration, or compatibility difference matters? |
| Old and new versions both fail | Did a shared dependency or data change affect both? |
| A direct database connection succeeds | Does the application identity, query, or transaction behave differently? |

Keep startup, connectivity, authorization, and schema compatibility separate. Before selecting rollback, establish whether the previous image can use the current data state. Verify checkout after mitigation; repeating the health check would repeat the original coverage gap.

## Operating references

- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/): The guide matching the failing application boundary. [Access and technical limits](../README.md#source-debug).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Prometheus alerting practices](https://prometheus.io/docs/practices/alerting/): Symptom-oriented alerting and response relevance. [Access and technical limits](../README.md#source-alerts).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).

[Back to DevOps Engineer resources](README.md) · [Browse this career collection](../README.md)

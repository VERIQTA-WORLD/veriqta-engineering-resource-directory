# DevOps Engineer: Labs and Portfolio Projects

## Build and trace a containerized service

Start with the Docker learning application, then document the path from source revision to an identifiable build result.

Retain application instructions, configuration sources, artifact identity, a meaningful functional check, and source attribution.

### Environment and access

Follow the selected upstream prerequisites. Docker software, Git, and registry or repository accounts may be required.

### Challenge the result

Change a configuration input in the dedicated lab. Compare startup success with application usability and explain the observed boundary.

The upstream tutorial was reviewed as a source; this extended project brief is not a pre-executed lab.

### Cleanup

Use the source cleanup instructions for containers and volumes. Remove public registry artifacts and disposable credentials separately where applicable.

### Implementation resources

- [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/) · [Access and limitations](../README.md#source-docker)
- [Pro Git, second edition](https://git-scm.com/book/en/v2) · [Access and limitations](../README.md#source-git)
- [GitHub Actions documentation](https://docs.github.com/en/actions) · [Access and limitations](../README.md#source-actions)

## Investigate a deployed application

Use a disposable local cluster and a synthetic application whose request path you can inspect.

Record client-to-service behavior, workload configuration, relevant observations, hypotheses, and the reasoning that identifies a bounded failure.

### Environment and access

Use version-compatible tools, a supported runtime, and adequate local capacity. Instrumentation is optional and needs its own setup.

### Challenge the result

Introduce one known configuration mismatch, then verify both the platform view and a functional request after recovery.

One controlled failure does not establish competence with every networking or cluster fault.

### Cleanup

Remove the dedicated workload and cluster using the upstream lifecycle instructions. Remove optional telemetry storage created for the exercise.

### Implementation resources

- [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) · [Access and limitations](../README.md#source-kind)
- [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) · [Access and limitations](../README.md#source-debug)
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/) · [Access and limitations](../README.md#source-otel)

## Write and rehearse a release decision

Create a release review for a synthetic service with a meaningful user journey and a potentially incompatible dependency.

Produce acceptance signals, exposure limits, stop conditions, a recovery decision table, and a communication note.

### Environment and access

You can perform the decision exercise without deployment. An optional implementation requires an authorized lab and synthetic data.

### Challenge the result

Assume low traffic hides a failing path. Explain what evidence is missing and whether to continue, pause, or add an appropriate test.

A design-only canary exercise cannot provide measured confidence or real traffic outcomes.

### Cleanup

Remove any optional deployment and retain sanitized observations. Label simulated outcomes separately from executed checks.

### Implementation resources

- [Canarying Releases](https://sre.google/workbook/canarying-releases/) · [Access and limitations](../README.md#source-canary)
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/) · [Access and limitations](../README.md#source-slo)
- [Incident Response](https://sre.google/workbook/incident-response/) · [Access and limitations](../README.md#source-incident)

[Back to DevOps Engineer resources](README.md) · [Browse this career collection](../README.md)

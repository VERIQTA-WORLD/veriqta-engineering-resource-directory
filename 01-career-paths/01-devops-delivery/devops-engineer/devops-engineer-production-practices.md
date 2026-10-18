# DevOps Engineer: Production Practice Resources

Use these resources to assess changes against actual service behavior. A green pipeline is a useful observation, but it is only one part of release evidence.

This page focuses on implementing and operating the path from source changes to usable services. **Question to keep in view:** Can you trace the deployed artifact to its source and establish whether users can use it?

## On this page

- [Define acceptance before deployment](#define-acceptance-before-deployment)
- [Investigate across boundaries](#investigate-across-boundaries)
- [Verify recovery and learn](#verify-recovery-and-learn)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Define acceptance before deployment

Choose functional checks and service signals that represent the affected user journey. Establish the baseline, observation period, and stop conditions. Low traffic may provide too little evidence for a confident release decision; identify another appropriate validation route.

## Investigate across boundaries

Compare timing, affected users, request paths, configuration, dependencies, and artifact identity. Preserve evidence before making unrelated changes. If reducing impact requires mitigation, record what it changed and what remains unknown about the cause.

## Verify recovery and learn

Confirm the intended user outcome after mitigation and inspect persistent side effects. Update the test or runbook that would have reduced uncertainty. Avoid turning a single incident's fix into a universal action for every similar-looking symptom.

## Apply guidance through an operating boundary

Start with the affected service, owner, current state, and authorized task. Establish a baseline and relevant acceptance evidence. Check data, identity, capacity, and recovery implications before proposing a change. After execution, verify the user or consumer outcome and any persistent side effects rather than relying only on a successful command.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Canarying Releases](https://sre.google/workbook/canarying-releases/)

**Use it to answer:** Does the release comparison have enough relevant exposure and signal to support continuing?

- **Start with:** Canary design, comparison signals, and decision criteria.
- **Prerequisites:** Deployment and service-observability familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-canary) for publisher context, access conditions, and the key limitation.

### [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)

**Use it to answer:** Which observable boundary separates the current symptom from the competing failure explanations?

- **Start with:** The guide matching the failing application boundary.
- **Prerequisites:** Workload, Service, and namespace familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-debug) for publisher context, access conditions, and the key limitation.

### [Incident Response](https://sre.google/workbook/incident-response/)

**Use it to answer:** Who coordinates response, preserves the timeline, and verifies that the affected service has recovered?

- **Start with:** Coordination, roles, communication, and follow-up.
- **Prerequisites:** Understanding of service ownership and operational impact.
- **Access and limits:** See the [maintained source annotation](../README.md#source-incident) for publisher context, access conditions, and the key limitation.

### [Prometheus alerting practices](https://prometheus.io/docs/practices/alerting/)

**Use it to answer:** What user or service condition requires action, and what can the responder reasonably do?

- **Start with:** Symptom-oriented alerting and response relevance.
- **Prerequisites:** Metrics and service-operation familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-alerts) for publisher context, access conditions, and the key limitation.

### [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/)

**Use it to answer:** Which signals can connect the user symptom to the dependency or operation you need to inspect?

- **Start with:** Signals relevant to your diagnostic question.
- **Prerequisites:** Basic distributed application and observability concepts.
- **Access and limits:** See the [maintained source annotation](../README.md#source-otel) for publisher context, access conditions, and the key limitation.

## Apply the reading

Write a release runbook for checkout. Include acceptance evidence, abort criteria, owner escalation, data-compatibility questions, and functional recovery verification. Use synthetic examples rather than customer data.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

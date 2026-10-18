# DevOps Architect: Production Practice Resources

Find resources for assessing whether a delivery design can be operated under actual change and failure. Use service evidence to evaluate the architecture after implementation.

This page focuses on designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership. **Question to keep in view:** Which boundaries and controls let teams release independently without losing operating accountability?

## On this page

- [Connect releases to user-visible evidence](#connect-releases-to-user-visible-evidence)
- [Treat recovery as a dependency problem](#treat-recovery-as-a-dependency-problem)
- [Review the shared system itself](#review-the-shared-system-itself)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Connect releases to user-visible evidence

Build success, rollout completion, and useful service behavior are distinct observations. Define which signals inform acceptance and how long they need to be observed. A canary only helps when its traffic, comparison, and failure coverage are meaningful.

## Treat recovery as a dependency problem

Reverting an application artifact may not reverse a schema change, credential rotation, or external side effect. Record compatible versions, data dependencies, and authority needed during recovery. Establish what must be restored and what can be rebuilt.

## Review the shared system itself

Delivery controllers, runners, registries, and telemetry pipelines need service ownership. Inspect failure isolation and upgrade coordination across teams. Use incidents and cost observations to revisit assumptions rather than preserving architecture decisions indefinitely.

## Apply guidance through an operating boundary

Start with the affected service, owner, current state, and authorized task. Establish a baseline and relevant acceptance evidence. Check data, identity, capacity, and recovery implications before proposing a change. After execution, verify the user or consumer outcome and any persistent side effects rather than relying only on a successful command.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Canarying Releases](https://sre.google/workbook/canarying-releases/)

**Use it to answer:** Does the release comparison have enough relevant exposure and signal to support continuing?

- **Start with:** Canary design, comparison signals, and decision criteria.
- **Prerequisites:** Deployment and service-observability familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-canary) for publisher context, access conditions, and the key limitation.

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

**Use it to answer:** Which user behavior should be measured, what target matters, and how will the result inform a decision?

- **Start with:** Selecting indicators, targets, and the improvement process.
- **Prerequisites:** Understanding of user-visible service behavior.
- **Access and limits:** See the [maintained source annotation](../README.md#source-slo) for publisher context, access conditions, and the key limitation.

### [Incident Response](https://sre.google/workbook/incident-response/)

**Use it to answer:** Who coordinates response, preserves the timeline, and verifies that the affected service has recovered?

- **Start with:** Coordination, roles, communication, and follow-up.
- **Prerequisites:** Understanding of service ownership and operational impact.
- **Access and limits:** See the [maintained source annotation](../README.md#source-incident) for publisher context, access conditions, and the key limitation.

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

**Use it to answer:** Can untrusted input or a dependency influence a job that holds consequential authority?

- **Start with:** Untrusted input, credentials, and third-party actions.
- **Prerequisites:** Understanding of triggers, jobs, and runner access.
- **Access and limits:** See the [maintained source annotation](../README.md#source-secure) for publisher context, access conditions, and the key limitation.

### [FinOps Framework](https://www.finops.org/framework/)

**Use it to answer:** Which cost is attributable to this capability, and what value or reliability requirement justifies it?

- **Start with:** Scope, allocation, ownership, and improvement capabilities.
- **Prerequisites:** Access to relevant usage, ownership, and billing context.
- **Access and limits:** See the [maintained source annotation](../README.md#source-finops) for publisher context, access conditions, and the key limitation.

## Apply the reading

Design a tabletop review in which the shared deployment service is unavailable during an application incident. Document the allowed recovery route, credential access, evidence needed, and actions that remain prohibited.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

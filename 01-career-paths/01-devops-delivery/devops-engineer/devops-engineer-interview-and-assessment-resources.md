# DevOps Engineer: Interview and Assessment Resources

Use these original prompts to practise tracing changes and explaining evidence. Good answers identify the next useful observation and the conditions behind a recovery choice.

This page focuses on implementing and operating the path from source changes to usable services. **Question to keep in view:** Can you trace the deployed artifact to its source and establish whether users can use it?

## On this page

- [Prompt: green pipeline, failed checkout](#prompt-green-pipeline-failed-checkout)
- [Prompt: works locally, fails after deployment](#prompt-works-locally-fails-after-deployment)
- [Prompt: rollback does not recover](#prompt-rollback-does-not-recover)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Prompt: green pipeline, failed checkout

The rollout completes and health checks pass, but checkout fails for some users. Ask what the health checks cover, which requests fail, what changed, and whether the database dependency is compatible. Distinguish a plausible hypothesis from an established cause.

## Prompt: works locally, fails after deployment

Compare artifact identity, startup, configuration, permissions, connectivity, and dependencies. Explain how you would narrow the boundary without changing several variables at once. A container image can reduce packaging differences while leaving important environmental differences.

## Prompt: rollback does not recover

The previous image starts, but errors continue after a data change. Explain the limitations of artifact rollback and the evidence needed to choose restoration or forward repair. Identify who owns the data decision.

## Assess reasoning with evidence

Explain what you know, what remains uncertain, and which observation you need next. Compare plausible alternatives before selecting an action. Make permission, user impact, and recovery conditions explicit. These are original practice prompts; they are not leaked employer questions, certification items, or claims about a universal hiring process.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)

**Use it to answer:** Which observable boundary separates the current symptom from the competing failure explanations?

- **Start with:** The guide matching the failing application boundary.
- **Prerequisites:** Workload, Service, and namespace familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-debug) for publisher context, access conditions, and the key limitation.

### [Canarying Releases](https://sre.google/workbook/canarying-releases/)

**Use it to answer:** Does the release comparison have enough relevant exposure and signal to support continuing?

- **Start with:** Canary design, comparison signals, and decision criteria.
- **Prerequisites:** Deployment and service-observability familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-canary) for publisher context, access conditions, and the key limitation.

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

### [Incident Response](https://sre.google/workbook/incident-response/)

**Use it to answer:** Who coordinates response, preserves the timeline, and verifies that the affected service has recovered?

- **Start with:** Coordination, roles, communication, and follow-up.
- **Prerequisites:** Understanding of service ownership and operational impact.
- **Access and limits:** See the [maintained source annotation](../README.md#source-incident) for publisher context, access conditions, and the key limitation.

## Apply the reading

Answer using an investigation table with observation, hypothesis, discriminating check, and interpretation. Include the point at which you would stop a release and involve a service or data owner.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Review your answer

| Dimension | A useful answer shows | A gap to investigate |
| --- | --- | --- |
| Scope | A clear affected system and constraints | A product choice before requirements |
| Evidence | Observations that separate explanations | A guessed cause presented as fact |
| Trade-offs | Alternatives and consequences | One unconditional best practice |
| Authority | Appropriate ownership and access | Unreviewed changes to shared systems |
| Recovery | Verification and persistent side effects | A retry or rollback with no conditions |

Attempt the reasoning before consulting the sources. If another person reviews your answer, ask which unsupported assumption most affects the recommendation.

## Sources and review scope

Prepared for VERIQTA on 18 October 2026. The linked primary-source entry pages were opened and reviewed for identity, scope, and the navigation supporting this selection. Full manuals, linked courses, and downstream examples were not reviewed in their entirety. No exercises or production changes were executed for this collection. Examples, project briefs, and decision aids are original VERIQTA editorial guidance. Use the applicable product version; access and hosted-service conditions can change.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

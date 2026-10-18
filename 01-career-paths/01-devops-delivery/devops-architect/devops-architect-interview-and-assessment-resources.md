# DevOps Architect: Interview and Assessment Resources

Use original design prompts and primary references to practise architecture reasoning. Evaluate how you discover constraints, compare options, and revise an answer when evidence changes.

This page focuses on designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership. **Question to keep in view:** Which boundaries and controls let teams release independently without losing operating accountability?

## On this page

- [Prompt: shared delivery capability](#prompt-shared-delivery-capability)
- [Prompt: a misleadingly successful rollout](#prompt-a-misleadingly-successful-rollout)
- [Prompt: a smaller operating team](#prompt-a-smaller-operating-team)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Prompt: shared delivery capability

Eight services use separate deployment scripts and a shared account. Ask about team ownership, release coupling, access, workload state, recovery needs, and current pain before proposing components. Explain what you would standardize first and what should remain application-specific.

## Prompt: a misleadingly successful rollout

A release passes pipeline checks and its infrastructure rollout completes, but a subset of users sees errors. Explain the missing acceptance evidence. Compare pausing, reducing exposure, reverting an artifact, and repairing forward in light of data compatibility.

## Prompt: a smaller operating team

Your preferred design requires a controller and a portal, but only one engineer can operate shared services. Reassess scope and managed alternatives. State what capability you would defer and which risk remains acceptable only with explicit stakeholder agreement.

## Assess reasoning with evidence

Explain what you know, what remains uncertain, and which observation you need next. Compare plausible alternatives before selecting an action. Make permission, user impact, and recovery conditions explicit. Use the prompts to practise explaining your assumptions, evidence, and decisions.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [C4 model](https://c4model.com/)

**Use it to answer:** Which people, systems, and execution boundaries must the audience understand before reviewing the design?

- **Start with:** System context, then container diagrams when more detail is needed.
- **Prerequisites:** Knowledge of the system and its dependencies.
- **Access and limits:** See the [maintained source annotation](../README.md#source-c4) for publisher context, access conditions, and the key limitation.

### [Architecture Decision Records](https://adr.github.io/)

**Use it to answer:** What alternatives did you consider, why did you choose this one, and when should the decision be revisited?

- **Start with:** The introductory explanation and a suitable template.
- **Prerequisites:** A decision with real alternatives and consequences.
- **Access and limits:** See the [maintained source annotation](../README.md#source-adr) for publisher context, access conditions, and the key limitation.

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

### [DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)

**Use it to answer:** Which technical practice or organizational dependency prevents a change from being released safely on demand?

- **Start with:** Implementing continuous delivery and common pitfalls.
- **Prerequisites:** Familiarity with a software change moving through a team.
- **Access and limits:** See the [maintained source annotation](../README.md#source-dora) for publisher context, access conditions, and the key limitation.

## Apply the reading

Answer one prompt with a requirements note, two options, a preferred decision, and a validation plan. Have another person change one constraint and assess whether your recommendation changes for a clear reason.

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

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

# DevOps Consultant: Interview and Assessment Resources

Use these original prompts to practise consulting judgment under incomplete evidence. A useful answer separates discovery, recommendation, authorized action, and verified outcome.

This page focuses on assessing delivery constraints, testing improvement hypotheses, and transferring usable capabilities to client teams. **Question to keep in view:** Which change addresses the demonstrated constraint, and what evidence would show it helped?

## On this page

- [Prompt: the sponsor wants Kubernetes](#prompt-the-sponsor-wants-kubernetes)
- [Prompt: a pilot looks faster](#prompt-a-pilot-looks-faster)
- [Prompt: handover is incomplete](#prompt-handover-is-incomplete)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Prompt: the sponsor wants Kubernetes

The sponsor asks for a migration to accelerate releases. Explain the evidence you would request before agreeing that orchestration addresses the constraint. Offer a bounded discovery plan and describe how you would communicate a different finding without dismissing the sponsor.

## Prompt: a pilot looks faster

Pipeline duration improves, but waiting for release approval grows and incidents increase. Explain which measures you would inspect and what conclusion the evidence supports. Avoid treating one improved measurement as proof of overall success.

## Prompt: handover is incomplete

Your prototype works, but the client has no owner for credentials, upgrades, or incident response. Explain what you can hand over now, what remains unaccepted, and how you would revise the engagement plan.

## Assess reasoning with evidence

Explain what you know, what remains uncertain, and which observation you need next. Compare plausible alternatives before selecting an action. Make permission, user impact, and recovery conditions explicit. These are original practice prompts; they are not leaked employer questions, certification items, or claims about a universal hiring process.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)

**Use it to answer:** Which technical practice or organizational dependency prevents a change from being released safely on demand?

- **Start with:** Implementing continuous delivery and common pitfalls.
- **Prerequisites:** Familiarity with a software change moving through a team.
- **Access and limits:** See the [maintained source annotation](../README.md#source-dora) for publisher context, access conditions, and the key limitation.

### [DORA: Software delivery performance metrics](https://dora.dev/guides/dora-metrics/)

**Use it to answer:** Which event definitions and service boundaries make a delivery measurement interpretable?

- **Start with:** Definitions and measurement boundaries.
- **Prerequisites:** A service boundary and accessible change records.
- **Access and limits:** See the [maintained source annotation](../README.md#source-metrics) for publisher context, access conditions, and the key limitation.

### [Architecture Decision Records](https://adr.github.io/)

**Use it to answer:** What alternatives did you consider, why did you choose this one, and when should the decision be revisited?

- **Start with:** The introductory explanation and a suitable template.
- **Prerequisites:** A decision with real alternatives and consequences.
- **Access and limits:** See the [maintained source annotation](../README.md#source-adr) for publisher context, access conditions, and the key limitation.

### [Incident Response](https://sre.google/workbook/incident-response/)

**Use it to answer:** Who coordinates response, preserves the timeline, and verifies that the affected service has recovered?

- **Start with:** Coordination, roles, communication, and follow-up.
- **Prerequisites:** Understanding of service ownership and operational impact.
- **Access and limits:** See the [maintained source annotation](../README.md#source-incident) for publisher context, access conditions, and the key limitation.

### [NIST SP 800-218: Secure Software Development Framework](https://csrc.nist.gov/pubs/sp/800/218/final)

**Use it to answer:** Which secure-development responsibility needs an owner, implementation control, and evidence?

- **Start with:** Publication scope and the practice groups relevant to your assessment.
- **Prerequisites:** Software lifecycle and security responsibility awareness.
- **Access and limits:** See the [maintained source annotation](../README.md#source-ssdf) for publisher context, access conditions, and the key limitation.

## Apply the reading

Answer with an evidence request, two hypotheses, a pilot proposal, and an honest success criterion. Identify an action you cannot take without client authority.

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

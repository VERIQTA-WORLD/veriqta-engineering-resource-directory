# DevOps Platform Engineer: Interview and Assessment Resources

Use these original prompts to practise platform product and engineering judgment. Evaluate the supported user task, the authority model, and operating behavior together.

This page focuses on providing supported delivery capabilities that other engineers can use through predictable interfaces. **Question to keep in view:** Can a team complete a supported workflow and recover from failure without depending on undocumented platform knowledge?

## On this page

- [Prompt: successful scaffolding, unusable service](#prompt-successful-scaffolding-unusable-service)
- [Prompt: one tenant can affect another](#prompt-one-tenant-can-affect-another)
- [Prompt: templates drift after generation](#prompt-templates-drift-after-generation)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Prompt: successful scaffolding, unusable service

A portal reports success, but the generated service cannot deploy. Identify the missing contract and status boundaries. Explain how you would locate external side effects and communicate partial completion without asking the user to understand every backend component.

## Prompt: one tenant can affect another

Two teams share an executor and a broad integration token. Explain how you would inspect the authority and failure boundaries, design a scoped alternative, and validate denied access. Do not treat separate UI views as isolation evidence.

## Prompt: templates drift after generation

A security fix updates the central template but existing repositories remain unchanged. Compare generated-code ownership, upgrade tooling, policy enforcement, and compatibility. Explain how you would measure adoption and handle exceptions.

## Assess reasoning with evidence

Explain what you know, what remains uncertain, and which observation you need next. Compare plausible alternatives before selecting an action. Make permission, user impact, and recovery conditions explicit. Use the prompts to practise explaining your assumptions, evidence, and decisions.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)

**Use it to answer:** Which supported capability helps the consumer complete a task, and who will operate it?

- **Start with:** Platform capabilities and the platform-as-product discussion.
- **Prerequisites:** Experience with developer workflows and operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-platforms) for publisher context, access conditions, and the key limitation.

### [Backstage Software Templates](https://backstage.io/docs/features/software-templates/)

**Use it to answer:** Which inputs become generated artifacts or external actions, and what remains after partial completion?

- **Start with:** Template structure and available actions.
- **Prerequisites:** A configured Backstage environment and integration knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-templates) for publisher context, access conditions, and the key limitation.

### [Backstage permissions overview](https://backstage.io/docs/permissions/overview/)

**Use it to answer:** Where is the permission decision enforced and which plugin or downstream action must respect it?

- **Start with:** Permission concepts and policy integration.
- **Prerequisites:** Backend development and authentication familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-permissions) for publisher context, access conditions, and the key limitation.

### [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows)

**Use it to answer:** How do consumers supply inputs and authority, and what happens when the shared contract changes?

- **Start with:** Inputs, secrets, permissions, and version references.
- **Prerequisites:** Working knowledge of a basic workflow.
- **Access and limits:** See the [maintained source annotation](../README.md#source-reuse) for publisher context, access conditions, and the key limitation.

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

**Use it to answer:** Which user behavior should be measured, what target matters, and how will the result inform a decision?

- **Start with:** Selecting indicators, targets, and the improvement process.
- **Prerequisites:** Understanding of user-visible service behavior.
- **Access and limits:** See the [maintained source annotation](../README.md#source-slo) for publisher context, access conditions, and the key limitation.

## Apply the reading

Answer with a platform contract, permission table, failure scenario, and consumer acceptance test. Explain what you would defer if the available platform operating capacity were cut in half.

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

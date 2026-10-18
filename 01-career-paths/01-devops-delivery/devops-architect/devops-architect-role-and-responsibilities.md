# DevOps Architect: Role and Responsibility Resources

Use these resources to identify the decisions behind a delivery architecture. Start with the change path and its constraints, then examine how responsibilities, controls, and recovery fit together.

This page focuses on designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership. **Question to keep in view:** Which boundaries and controls let teams release independently without losing operating accountability?

## On this page

- [Connect architecture to delivery outcomes](#connect-architecture-to-delivery-outcomes)
- [Define decisions and ownership together](#define-decisions-and-ownership-together)
- [Make acceptance reviewable](#make-acceptance-reviewable)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Connect architecture to delivery outcomes

Trace one representative change from source to a verified user outcome. Identify waiting, rework, and dependencies before deciding which components should change. A technically elegant pipeline may leave the main delay untouched if approval ownership, test reliability, or data coordination remains unresolved.

## Define decisions and ownership together

For each boundary, name who provides it, who consumes it, and who responds when it fails. Separate a shared delivery capability from an application-specific decision. A central standard can reduce inconsistency, but centralizing every release decision can also create a queue that prevents independent delivery.

## Make acceptance reviewable

Translate requirements into observable scenarios: an expired credential, an unavailable registry, a failed rollout, and a restore request. Record assumptions and unresolved risks. Review the design with the teams who will implement and operate it; their capacity is part of feasibility.

## Read by responsibility

Begin with the reference that explains the outcome or boundary you need to own. Follow implementation documentation only after you can name the decision and its acceptance evidence. Use the resources to clarify responsibilities with the relevant team rather than treating the role title as a fixed job description.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)

**Use it to answer:** Which technical practice or organizational dependency prevents a change from being released safely on demand?

- **Start with:** Implementing continuous delivery and common pitfalls.
- **Prerequisites:** Familiarity with a software change moving through a team.
- **Access and limits:** See the [maintained source annotation](../README.md#source-dora) for publisher context, access conditions, and the key limitation.

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

### [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)

**Use it to answer:** Which supported capability helps the consumer complete a task, and who will operate it?

- **Start with:** Platform capabilities and the platform-as-product discussion.
- **Prerequisites:** Experience with developer workflows and operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-platforms) for publisher context, access conditions, and the key limitation.

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

**Use it to answer:** Which user behavior should be measured, what target matters, and how will the result inform a decision?

- **Start with:** Selecting indicators, targets, and the improvement process.
- **Prerequisites:** Understanding of user-visible service behavior.
- **Access and limits:** See the [maintained source annotation](../README.md#source-slo) for publisher context, access conditions, and the key limitation.

## Apply the reading

Choose one service. Produce a change-path map, responsibility table, and three measurable acceptance scenarios. Ask which requirement would invalidate your preferred design and document an alternative.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

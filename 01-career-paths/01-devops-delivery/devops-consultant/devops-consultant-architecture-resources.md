# DevOps Consultant: Architecture Resources

Use architecture methods to compare feasible improvement options within the client context. A target architecture needs an adoption path and an operating owner.

This page focuses on assessing delivery constraints, testing improvement hypotheses, and transferring usable capabilities to client teams. **Question to keep in view:** Which change addresses the demonstrated constraint, and what evidence would show it helped?

## On this page

- [Map the current delivery boundary](#map-the-current-delivery-boundary)
- [Design a staged transition](#design-a-staged-transition)
- [Transfer decision ownership](#transfer-decision-ownership)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Map the current delivery boundary

Show people, systems, permissions, and external dependencies that affect a representative change. Mark confirmed relationships separately from assumptions. The purpose is to locate constraints and risks, not to create an exhaustive diagram of every installed product.

## Design a staged transition

Select a pilot boundary with a willing owner and a manageable recovery path. Explain which interfaces remain unchanged and where temporary duplication is necessary. Include a decision point for stopping or revising the migration when evidence does not support expansion.

## Transfer decision ownership

Record alternatives, rejected options, validation results, and unresolved dependencies. Have client maintainers review the design through realistic failure scenarios. A handover should let them reason about future changes rather than merely reproduce your setup.

## Compare defensible alternatives

State requirements, constraints, and failure assumptions before selecting components. Compare at least two feasible options and record consequences, operating owners, and unresolved questions. Identify a specific observation that would change the decision. Use diagrams to clarify dependencies and authority, then validate the consequential behavior separately.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [C4 model](https://c4model.com/)

**Use it to answer:** Which people, systems, and execution boundaries must the audience understand before reviewing the design?

- **Start with:** System context, then container diagrams when more detail is needed.
- **Prerequisites:** Knowledge of the system and its dependencies.
- **Access and limits:** See the [maintained source annotation](../README.md#source-c4) for publisher context, access conditions, and the key limitation.

### [arc42](https://arc42.org/)

**Use it to answer:** Which quality requirement, interface, or operating risk is missing from the current design explanation?

- **Start with:** The template overview and quality requirements.
- **Prerequisites:** An identifiable system boundary and stakeholders.
- **Access and limits:** See the [maintained source annotation](../README.md#source-arc) for publisher context, access conditions, and the key limitation.

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

### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

**Use it to answer:** Which workload assumption needs review across reliability, security, operations, performance, cost, or sustainability?

- **Start with:** The framework overview and the pillar relevant to your review.
- **Prerequisites:** A defined workload and stakeholder requirements.
- **Access and limits:** See the [maintained source annotation](../README.md#source-aws) for publisher context, access conditions, and the key limitation.

## Apply the reading

Prepare current and proposed delivery views for the client scenario. Add a pilot, acceptance evidence, operating owner, and exit plan if the intervention fails to reduce the demonstrated constraint.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

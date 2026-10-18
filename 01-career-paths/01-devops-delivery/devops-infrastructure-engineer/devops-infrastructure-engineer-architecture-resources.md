# DevOps Infrastructure Engineer: Architecture Resources

Use these references to design infrastructure that can be changed and recovered within explicit ownership boundaries. Model control dependencies as well as application dependencies.

This page focuses on building and maintaining the compute, networking, identity, configuration, and state foundations behind software delivery. **Question to keep in view:** Can you change or rebuild infrastructure without losing control of state, access, data, and recovery?

## On this page

- [Map the control plane](#map-the-control-plane)
- [Define state and failure boundaries](#define-state-and-failure-boundaries)
- [Account for persistent data](#account-for-persistent-data)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Map the control plane

Show where definitions, state, credentials, runners, and configuration inventories live. Identify dependencies needed to perform a change. If the recovery process depends on a service inside the failed environment, provide a credible alternate route.

## Define state and failure boundaries

Separate environments or resource groups according to ownership and impact where justified. Smaller boundaries can reduce blast radius but introduce coordination and dependency management. Compare options using actual change patterns and recovery requirements.

## Account for persistent data

Document which resources hold valuable data and which references merely recreate empty capacity. Review deletion protection, retention, restore authority, and service acceptance with the data owner. A reproducible environment is not a substitute for a verified restore.

## Compare defensible alternatives

State requirements, constraints, and failure assumptions before selecting components. Compare at least two feasible options and record consequences, operating owners, and unresolved questions. Identify a specific observation that would change the decision. Use diagrams to clarify dependencies and authority, then validate the consequential behavior separately.

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

### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

**Use it to answer:** Which workload assumption needs review across reliability, security, operations, performance, cost, or sustainability?

- **Start with:** The framework overview and the pillar relevant to your review.
- **Prerequisites:** A defined workload and stakeholder requirements.
- **Access and limits:** See the [maintained source annotation](../README.md#source-aws) for publisher context, access conditions, and the key limitation.

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

**Use it to answer:** Which policy layers determine whether the execution identity can perform the requested action?

- **Start with:** Policy types and the linked evaluation guidance.
- **Prerequisites:** AWS identities, resources, and basic JSON familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-iam) for publisher context, access conditions, and the key limitation.

## Apply the reading

Draw the change-control dependencies for the shared environment scenario. Identify two circular recovery dependencies and propose ways to break them without granting permanent unrestricted access.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

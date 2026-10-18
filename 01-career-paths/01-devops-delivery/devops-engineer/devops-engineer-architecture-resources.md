# DevOps Engineer: Architecture Resources

Use these references to understand the architecture of a delivery path without turning every application into a platform project. Start with the interfaces that affect repeatability and recovery.

This page focuses on implementing and operating the path from source changes to usable services. **Question to keep in view:** Can you trace the deployed artifact to its source and establish whether users can use it?

## On this page

- [Draw two connected paths](#draw-two-connected-paths)
- [Design environment differences deliberately](#design-environment-differences-deliberately)
- [Include a practical recovery route](#include-a-practical-recovery-route)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Draw two connected paths

Show how a source change becomes a deployed artifact and how a user request reaches the running service. Connect them through configuration, identity, and version information. This prevents a pipeline-only view of service acceptance.

## Design environment differences deliberately

List which differences are required, such as credentials and capacity, and which are accidental. Make configuration sources and ownership explicit. Similar manifests do not guarantee similar behavior when dependencies, data, or policies differ.

## Include a practical recovery route

State how you select a previous artifact, verify compatibility, and assess user impact. Identify data changes that cannot be undone by redeployment. Keep the recovery route within the access and skills available to the responder.

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

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [Canarying Releases](https://sre.google/workbook/canarying-releases/)

**Use it to answer:** Does the release comparison have enough relevant exposure and signal to support continuing?

- **Start with:** Canary design, comparison signals, and decision criteria.
- **Prerequisites:** Deployment and service-observability familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-canary) for publisher context, access conditions, and the key limitation.

### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

**Use it to answer:** Which workload assumption needs review across reliability, security, operations, performance, cost, or sustainability?

- **Start with:** The framework overview and the pillar relevant to your review.
- **Prerequisites:** A defined workload and stakeholder requirements.
- **Access and limits:** See the [maintained source annotation](../README.md#source-aws) for publisher context, access conditions, and the key limitation.

## Apply the reading

Produce a delivery diagram and a request-path diagram for the checkout scenario. Mark the changed configuration and database dependency, then identify observations needed before selecting a recovery action.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

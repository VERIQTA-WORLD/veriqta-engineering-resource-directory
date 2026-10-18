# DevOps Architect: Architecture Resources

Use these references to produce a design that another engineer can challenge and implement. Begin with requirements, dependencies, and failure assumptions rather than a diagram of preferred products.

This page focuses on designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership. **Question to keep in view:** Which boundaries and controls let teams release independently without losing operating accountability?

## On this page

- [Define the delivery system boundary](#define-the-delivery-system-boundary)
- [Compare quality scenarios](#compare-quality-scenarios)
- [Design the operating model](#design-the-operating-model)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Define the delivery system boundary

Include repositories, build execution, artifact publication, credentials, deployment targets, and runtime evidence. Show external dependencies and the identities crossing each boundary. Make it possible to see where untrusted changes could encounter production authority.

## Compare quality scenarios

Ask how the design behaves when a registry is unavailable, a deployment is partially applied, a shared controller fails, or a service must restore data. Compare options against the same scenarios. The right answer may be different for a small stateless service and a regulated data workload.

## Design the operating model

Assign owners for controller upgrades, incident response, credential renewal, exception handling, and decommissioning. A design that can only be operated by its author is incomplete. Review the cost and responsibility of every shared component before calling it a standard.

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

### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

**Use it to answer:** Which workload assumption needs review across reliability, security, operations, performance, cost, or sustainability?

- **Start with:** The framework overview and the pillar relevant to your review.
- **Prerequisites:** A defined workload and stakeholder requirements.
- **Access and limits:** See the [maintained source annotation](../README.md#source-aws) for publisher context, access conditions, and the key limitation.

### [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)

**Use it to answer:** Which supported capability helps the consumer complete a task, and who will operate it?

- **Start with:** Platform capabilities and the platform-as-product discussion.
- **Prerequisites:** Experience with developer workflows and operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-platforms) for publisher context, access conditions, and the key limitation.

## Apply the reading

Prepare a context diagram, a trust-boundary explanation, and two decision records for the eight-service scenario. Include a staged adoption plan that leaves teams able to release while migration proceeds.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

## Sources and review scope

Prepared for VERIQTA on 18 October 2026. The linked primary-source entry pages were opened and reviewed for identity, scope, and the navigation supporting this selection. Full manuals, linked courses, and downstream examples were not reviewed in their entirety. No exercises or production changes were executed for this collection. Examples, project briefs, and decision aids are original VERIQTA editorial guidance. Use the applicable product version; access and hosted-service conditions can change.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

# DevOps Architect: Tools and Technology Resources

Compare technologies by the responsibility they take on in the delivery architecture. Choose the simplest combination that can satisfy the stated requirements and be operated by the available team.

This page focuses on designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership. **Question to keep in view:** Which boundaries and controls let teams release independently without losing operating accountability?

## On this page

- [Compare responsibilities before products](#compare-responsibilities-before-products)
- [Account for operating cost](#account-for-operating-cost)
- [Make adoption reversible where practical](#make-adoption-reversible-where-practical)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Compare responsibilities before products

Separate workflow execution, infrastructure lifecycle, artifact storage, application reconciliation, policy evaluation, and telemetry. One product may span several concerns, but its convenience does not erase the different trust boundaries. Identify which system is authoritative for each kind of state.

## Account for operating cost

A managed workflow service reduces some maintenance while imposing account, usage, and integration constraints. A self-managed controller offers control but introduces patching, backup, capacity, and incident work. Include human operating time in the comparison.

## Make adoption reversible where practical

Define interfaces around inputs, outputs, artifact identity, and policy decisions rather than relying on undocumented product behavior. Portability has a cost, so protect the boundaries most likely to change. Require a migration plan for shared capabilities that many teams depend on.

## Compare tools against the same task

For each candidate, record the responsibility it owns, its inputs and outputs, required authority, stored state, operator burden, and failure behavior. Reject options that cannot satisfy a mandatory requirement. Compare remaining options using the same workload and team assumptions; a longer feature list is not a decision criterion by itself.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/)

**Use it to answer:** Which desired state is authoritative, what can the reconciler change, and how is disagreement exposed?

- **Start with:** Core concepts, then the relevant user guide.
- **Prerequisites:** Kubernetes resources, Git, and application deployment knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-argo) for publisher context, access conditions, and the key limitation.

### [OPA policy language](https://www.openpolicyagent.org/docs/policy-language)

**Use it to answer:** What decision is evaluated from the input, and which component enforces that result?

- **Start with:** Language examples, input documents, and rule evaluation.
- **Prerequisites:** Structured data and basic authorization concepts.
- **Access and limits:** See the [maintained source annotation](../README.md#source-opa) for publisher context, access conditions, and the key limitation.

### [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/)

**Use it to answer:** Which signals can connect the user symptom to the dependency or operation you need to inspect?

- **Start with:** Signals relevant to your diagnostic question.
- **Prerequisites:** Basic distributed application and observability concepts.
- **Access and limits:** See the [maintained source annotation](../README.md#source-otel) for publisher context, access conditions, and the key limitation.

## Apply the reading

Compare two delivery designs for the same service: a repository-driven workflow and a shared reconciliation service. Record control boundaries, required operators, failure behavior, and the evidence needed to prefer one.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

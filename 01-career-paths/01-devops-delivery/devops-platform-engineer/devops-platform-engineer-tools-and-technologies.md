# DevOps Platform Engineer: Tools and Technology Resources

Select platform components for capabilities you have evidence to support. A catalog, scaffolder, policy engine, reconciler, and telemetry pipeline have distinct responsibilities.

This page focuses on providing supported delivery capabilities that other engineers can use through predictable interfaces. **Question to keep in view:** Can a team complete a supported workflow and recover from failure without depending on undocumented platform knowledge?

## On this page

- [Separate discoverability from execution](#separate-discoverability-from-execution)
- [Make integration authority explicit](#make-integration-authority-explicit)
- [Choose a manageable service footprint](#choose-a-manageable-service-footprint)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Separate discoverability from execution

A catalog can help users find services and owners. A template can generate artifacts or call integrations. Neither automatically establishes runtime access or operating accountability. Choose the smallest interface that lets users complete the intended task reliably.

## Make integration authority explicit

Review the identity and permission scope used by each action. Keep consumer authorization separate from executor credentials. Validate external side effects and provide a way to discover partial completion after a frontend or backend failure.

## Choose a manageable service footprint

Every new component adds upgrades, configuration, credentials, and incident work. A repository template or reusable workflow may satisfy an early need with less operating burden than a full portal. Reassess when usage and support evidence justify more capability.

## Compare tools against the same task

For each candidate, record the responsibility it owns, its inputs and outputs, required authority, stored state, operator burden, and failure behavior. Reject options that cannot satisfy a mandatory requirement. Compare remaining options using the same workload and team assumptions; a longer feature list is not a decision criterion by itself.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Backstage Software Catalog](https://backstage.io/docs/features/software-catalog/)

**Use it to answer:** Which metadata describes the service and its owner, and how will stale information be detected?

- **Start with:** Entity concepts and ownership information.
- **Prerequisites:** Application-development familiarity and an appropriate Backstage environment.
- **Access and limits:** See the [maintained source annotation](../README.md#source-catalog) for publisher context, access conditions, and the key limitation.

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

### [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/)

**Use it to answer:** Which desired state is authoritative, what can the reconciler change, and how is disagreement exposed?

- **Start with:** Core concepts, then the relevant user guide.
- **Prerequisites:** Kubernetes resources, Git, and application deployment knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-argo) for publisher context, access conditions, and the key limitation.

## Apply the reading

Compare a repository template with a portal-based onboarding workflow. Evaluate authorization, user feedback, support cost, partial failure, versioning, and the evidence that would justify the larger service.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

# DevOps Architect: Skills and Prerequisite Resources

Find resources for the assumptions you need to defend before designing delivery systems. Architectural breadth is useful only when you can connect it to the behavior of real components.

This page focuses on designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership. **Question to keep in view:** Which boundaries and controls let teams release independently without losing operating accountability?

## On this page

- [Develop implementation literacy](#develop-implementation-literacy)
- [Reason about state and failure](#reason-about-state-and-failure)
- [Communicate constraints precisely](#communicate-constraints-precisely)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Develop implementation literacy

You should be able to trace a process, a request, an artifact, and a permission decision. Use a small implementation to expose uncertainty in your mental model. You do not need equal depth in every tool, but you need to know when a specialist review is necessary.

## Reason about state and failure

Distinguish source history, desired configuration, infrastructure state, persistent application data, and runtime status. They change through different mechanisms. A rollback plan that treats all five as the same object can restore a manifest while leaving the service unusable.

## Communicate constraints precisely

Practise expressing availability, isolation, recovery, and cost as conditions a design can be evaluated against. Learn to separate a requirement from an implementation preference. Record what is unknown instead of concealing it with a detailed diagram.

## Choose the next knowledge gap

Explain the relevant mechanism before selecting an exercise. If you cannot trace the identity, state, request, or result, use the corresponding foundation first. Move to implementation references when you can describe what you expect to observe. You do not need to read every selected source in sequence.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Pro Git, second edition](https://git-scm.com/book/en/v2)

**Use it to answer:** Which source changes and references explain the artifact or configuration being reviewed?

- **Start with:** Git Basics, then branching and the internals relevant to your question.
- **Prerequisites:** Basic command-line familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-git) for publisher context, access conditions, and the key limitation.

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [Kubernetes overview](https://kubernetes.io/docs/concepts/overview/)

**Use it to answer:** Which orchestration responsibility is necessary for this workload, and what remains the application owner's concern?

- **Start with:** What Kubernetes does and the linked concepts.
- **Prerequisites:** Containers, basic networking, and application configuration.
- **Access and limits:** See the [maintained source annotation](../README.md#source-kube) for publisher context, access conditions, and the key limitation.

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

**Use it to answer:** Which policy layers determine whether the execution identity can perform the requested action?

- **Start with:** Policy types and the linked evaluation guidance.
- **Prerequisites:** AWS identities, resources, and basic JSON familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-iam) for publisher context, access conditions, and the key limitation.

### [arc42](https://arc42.org/)

**Use it to answer:** Which quality requirement, interface, or operating risk is missing from the current design explanation?

- **Start with:** The template overview and quality requirements.
- **Prerequisites:** An identifiable system boundary and stakeholders.
- **Access and limits:** See the [maintained source annotation](../README.md#source-arc) for publisher context, access conditions, and the key limitation.

## Apply the reading

Explain a deployment using four views: source and artifact identity, runtime request path, authorization boundaries, and recovery dependencies. Identify one assumption in each view that you cannot yet verify.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

## Sources and review scope

Prepared for VERIQTA on 18 October 2026. The linked primary-source entry pages were opened and reviewed for identity, scope, and the navigation supporting this selection. Full manuals, linked courses, and downstream examples were not reviewed in their entirety. No exercises or production changes were executed for this collection. Examples, project briefs, and decision aids are original VERIQTA editorial guidance. Use the applicable product version; access and hosted-service conditions can change.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

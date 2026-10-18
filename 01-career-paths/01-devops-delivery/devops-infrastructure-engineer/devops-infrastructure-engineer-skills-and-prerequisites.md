# DevOps Infrastructure Engineer: Skills and Prerequisite Resources

Choose references for the infrastructure mechanisms you need to explain before automating a lifecycle. Focus on state, host behavior, access, dependencies, and evidence.

This page focuses on building and maintaining the compute, networking, identity, configuration, and state foundations behind software delivery. **Question to keep in view:** Can you change or rebuild infrastructure without losing control of state, access, data, and recovery?

## On this page

- [Understand host and network dependencies](#understand-host-and-network-dependencies)
- [Develop state and provider literacy](#develop-state-and-provider-literacy)
- [Practise permission and recovery reasoning](#practise-permission-and-recovery-reasoning)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Understand host and network dependencies

Explain how a service starts, where configuration is read, which ports it uses, and what storage or network services it depends on. Understand the installed operating environment before treating a successful provisioning operation as a usable workload.

## Develop state and provider literacy

Read how the infrastructure tool maps configuration to managed resources. Inspect provider assumptions and backend behavior. Distinguish a configuration change, a state change, and an external manual modification; they are related but not equivalent.

## Practise permission and recovery reasoning

Identify the identity performing an action and the policy layers affecting it. Test denied operations in a disposable environment. Learn how access to state or backups may expose sensitive material even when no workload endpoint is public.

## Choose the next knowledge gap

Explain the relevant mechanism before selecting an exercise. If you cannot trace the identity, state, request, or result, use the corresponding foundation first. Move to implementation references when you can describe what you expect to observe. You do not need to read every selected source in sequence.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html)

**Use it to answer:** What establishes startup completion and how does process behavior interact with service supervision?

- **Start with:** Service type, process startup, and restart behavior.
- **Prerequisites:** Linux service administration and the installed systemd version.
- **Access and limits:** See the [maintained source annotation](../README.md#source-systemd) for publisher context, access conditions, and the key limitation.

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking)

**Use it to answer:** What evidence distinguishes a currently active operation from an abandoned lock?

- **Start with:** Lock behavior and force-unlock conditions.
- **Prerequisites:** Understanding of the selected backend and active operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-locking) for publisher context, access conditions, and the key limitation.

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

**Use it to answer:** Which policy layers determine whether the execution identity can perform the requested action?

- **Start with:** Policy types and the linked evaluation guidance.
- **Prerequisites:** AWS identities, resources, and basic JSON familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-iam) for publisher context, access conditions, and the key limitation.

### [Pro Git, second edition](https://git-scm.com/book/en/v2)

**Use it to answer:** Which source changes and references explain the artifact or configuration being reviewed?

- **Start with:** Git Basics, then branching and the internals relevant to your question.
- **Prerequisites:** Basic command-line familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-git) for publisher context, access conditions, and the key limitation.

## Apply the reading

Explain a configuration-managed service from resource creation through startup. List three dependencies outside the provisioning definition and how each would be verified.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

## Sources and review scope

Prepared for VERIQTA on 18 October 2026. The linked primary-source entry pages were opened and reviewed for identity, scope, and the navigation supporting this selection. Full manuals, linked courses, and downstream examples were not reviewed in their entirety. No exercises or production changes were executed for this collection. Examples, project briefs, and decision aids are original VERIQTA editorial guidance. Use the applicable product version; access and hosted-service conditions can change.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

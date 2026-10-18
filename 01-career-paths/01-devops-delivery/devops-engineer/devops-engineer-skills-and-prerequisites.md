# DevOps Engineer: Skills and Prerequisite Resources

Build the foundations needed to explain a deployment failure across process, network, configuration, identity, and data boundaries. Use practical evidence to choose your next learning gap.

This page focuses on implementing and operating the path from source changes to usable services. **Question to keep in view:** Can you trace the deployed artifact to its source and establish whether users can use it?

## On this page

- [Understand the running application](#understand-the-running-application)
- [Understand changes and authority](#understand-changes-and-authority)
- [Practise diagnostic interpretation](#practise-diagnostic-interpretation)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Understand the running application

Identify its process, startup requirements, listener, configuration, logs, and persistence needs. Learn how the service is supervised and how to observe a failed start. Container packaging changes delivery mechanics but does not remove these application dependencies.

## Understand changes and authority

Use version control to inspect differences, infrastructure state to understand resource ownership, and identity references to reason about allowed actions. Treat build access and production access as separate concerns. Know which credentials are available to each job.

## Practise diagnostic interpretation

Differentiate a name-resolution failure, connection failure, HTTP error, and application-level error. Collect evidence that separates hypotheses. A status flag can tell you where to look without explaining the user-visible problem.

## Choose the next knowledge gap

Explain the relevant mechanism before selecting an exercise. If you cannot trace the identity, state, request, or result, use the corresponding foundation first. Move to implementation references when you can describe what you expect to observe. You do not need to read every selected source in sequence.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Pro Git, second edition](https://git-scm.com/book/en/v2)

**Use it to answer:** Which source changes and references explain the artifact or configuration being reviewed?

- **Start with:** Git Basics, then branching and the internals relevant to your question.
- **Prerequisites:** Basic command-line familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-git) for publisher context, access conditions, and the key limitation.

### [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html)

**Use it to answer:** What establishes startup completion and how does process behavior interact with service supervision?

- **Start with:** Service type, process startup, and restart behavior.
- **Prerequisites:** Linux service administration and the installed systemd version.
- **Access and limits:** See the [maintained source annotation](../README.md#source-systemd) for publisher context, access conditions, and the key limitation.

### [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/)

**Use it to answer:** How do the application image, runtime configuration, network exposure, and persistent data relate?

- **Start with:** Before you start, then the application workflow.
- **Prerequisites:** Docker software, Git, and the account requirements in the guide.
- **Access and limits:** See the [maintained source annotation](../README.md#source-docker) for publisher context, access conditions, and the key limitation.

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

For a small application, document the request path and deployment path separately. Identify where configuration enters each and which observations would reveal a failure.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

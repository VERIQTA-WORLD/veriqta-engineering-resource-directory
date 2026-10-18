# DevOps Engineer: Learning Resources

Learn delivery engineering through one application that you can build, run, change, and investigate. Use the resources below to connect foundations with service operation.

This page focuses on implementing and operating the path from source changes to usable services. **Question to keep in view:** Can you trace the deployed artifact to its source and establish whether users can use it?

## On this page

- [Begin with source and a runnable result](#begin-with-source-and-a-runnable-result)
- [Add delivery feedback](#add-delivery-feedback)
- [Extend into operations](#extend-into-operations)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Begin with source and a runnable result

Learn enough Git to inspect a change and enough container behavior to explain the resulting application. Keep your first implementation small. Record instructions that another person can follow without depending on your shell history.

## Add delivery feedback

Introduce a workflow that checks an understandable property before publishing or deploying. Prefer a meaningful application check over a large collection of unrelated jobs. Explain which failures the check detects and which remain outside its coverage.

## Extend into operations

Study reliability and troubleshooting once the application runs. Introduce a bounded misconfiguration in a lab and recover it. The learning outcome is your explanation of the evidence, not merely returning the environment to a green status.

## Use a reading and practice loop

Choose one question, read the relevant section, explain it in your own words, and apply it to a small example. Record what the source established and what you still need to investigate. If the example cannot be run within your budget or authority, label the work design-only and write a validation plan.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Pro Git, second edition](https://git-scm.com/book/en/v2)

**Use it to answer:** Which source changes and references explain the artifact or configuration being reviewed?

- **Start with:** Git Basics, then branching and the internals relevant to your question.
- **Prerequisites:** Basic command-line familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-git) for publisher context, access conditions, and the key limitation.

### [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/)

**Use it to answer:** How do the application image, runtime configuration, network exposure, and persistent data relate?

- **Start with:** Before you start, then the application workflow.
- **Prerequisites:** Docker software, Git, and the account requirements in the guide.
- **Access and limits:** See the [maintained source annotation](../README.md#source-docker) for publisher context, access conditions, and the key limitation.

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

### [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)

**Use it to answer:** Which observable boundary separates the current symptom from the competing failure explanations?

- **Start with:** The guide matching the failing application boundary.
- **Prerequisites:** Workload, Service, and namespace familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-debug) for publisher context, access conditions, and the key limitation.

### [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)

**Use it to answer:** Which reliability responsibility needs better evidence, ownership, or an operating procedure?

- **Start with:** The chapter corresponding to your current service concern.
- **Prerequisites:** Experience operating a service.
- **Access and limits:** See the [maintained source annotation](../README.md#source-sre) for publisher context, access conditions, and the key limitation.

## Apply the reading

Build a learning sequence with three outcomes: reproducible local execution, a traceable artifact, and functional verification after a change. Choose a reference for each gap and define what evidence you will retain.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

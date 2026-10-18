# DevOps Engineer: Role and Responsibility Resources

Use these resources to connect source changes, artifacts, infrastructure, and service behavior. Your work makes the delivery path understandable and operable across the teams involved.

This page focuses on implementing and operating the path from source changes to usable services. **Question to keep in view:** Can you trace the deployed artifact to its source and establish whether users can use it?

## On this page

- [Trace changes through the delivery path](#trace-changes-through-the-delivery-path)
- [Operate the interfaces between teams](#operate-the-interfaces-between-teams)
- [Close the loop after release](#close-the-loop-after-release)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Trace changes through the delivery path

Identify which source revision produced the artifact, how it was configured, where it was deployed, and how acceptance was checked. Preserve identities across those stages. Rebuilding an artifact separately in each environment can make comparisons harder to explain.

## Operate the interfaces between teams

Agree application configuration, deployment requirements, data coordination, permissions, and response ownership. Pipeline implementation cannot compensate for an application whose startup or health behavior is unknown. Ask the relevant owner to define what useful operation means.

## Close the loop after release

Inspect service outcomes and investigate failures with evidence. Feed recurring issues back into tests, configuration management, and runbooks. Automation should reduce repeated uncertainty rather than hide it behind a successful workflow status.

## Read by responsibility

Begin with the reference that explains the outcome or boundary you need to own. Follow implementation documentation only after you can name the decision and its acceptance evidence. Use the resources to clarify responsibilities with the relevant team rather than treating the role title as a fixed job description.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)

**Use it to answer:** Which technical practice or organizational dependency prevents a change from being released safely on demand?

- **Start with:** Implementing continuous delivery and common pitfalls.
- **Prerequisites:** Familiarity with a software change moving through a team.
- **Access and limits:** See the [maintained source annotation](../README.md#source-dora) for publisher context, access conditions, and the key limitation.

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

### [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/)

**Use it to answer:** How do the application image, runtime configuration, network exposure, and persistent data relate?

- **Start with:** Before you start, then the application workflow.
- **Prerequisites:** Docker software, Git, and the account requirements in the guide.
- **Access and limits:** See the [maintained source annotation](../README.md#source-docker) for publisher context, access conditions, and the key limitation.

### [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)

**Use it to answer:** Which observable boundary separates the current symptom from the competing failure explanations?

- **Start with:** The guide matching the failing application boundary.
- **Prerequisites:** Workload, Service, and namespace familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-debug) for publisher context, access conditions, and the key limitation.

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

**Use it to answer:** Which user behavior should be measured, what target matters, and how will the result inform a decision?

- **Start with:** Selecting indicators, targets, and the improvement process.
- **Prerequisites:** Understanding of user-visible service behavior.
- **Access and limits:** See the [maintained source annotation](../README.md#source-slo) for publisher context, access conditions, and the key limitation.

## Apply the reading

Trace one application change from commit to functional verification. Record artifact identity, configuration, deployment destination, acceptance checks, and the owner of each dependency.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

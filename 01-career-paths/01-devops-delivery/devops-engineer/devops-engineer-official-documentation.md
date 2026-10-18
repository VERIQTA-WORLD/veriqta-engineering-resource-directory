# DevOps Engineer: Official Documentation

Use these references to confirm workflow, runtime, and permission behavior while implementing the delivery path. Match each source to the system and release actually in use.

This page focuses on implementing and operating the path from source changes to usable services. **Question to keep in view:** Can you trace the deployed artifact to its source and establish whether users can use it?

## On this page

- [Read the implementation contract](#read-the-implementation-contract)
- [Check runtime behavior separately](#check-runtime-behavior-separately)
- [Keep a claim-to-setting map](#keep-a-claim-to-setting-map)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Read the implementation contract

Check triggers, job permissions, environment configuration, and dependencies before adapting a workflow example. Confirm whether a change can be initiated by untrusted input. Record which settings come from the repository and which are controlled elsewhere.

## Check runtime behavior separately

Use application and platform documentation to understand startup, readiness, service routing, and diagnostic access. A successful deployment API call establishes a different fact from a working user request. Verify each boundary with the appropriate evidence.

## Keep a claim-to-setting map

For consequential behavior, record the reference, local configuration, and proposed test. Examples include deployment approval, artifact selection, target identity, and failure detection. Unknown behavior should remain an explicit question until validated.

## Build a claim-to-evidence record

Write the claim you need to validate, identify the applicable reference section and release, then inspect the actual local setting. Use a controlled test when configuration or integration behavior remains uncertain. Keep unsupported assumptions visible. A published capability and a working local control are different pieces of evidence.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

**Use it to answer:** Can untrusted input or a dependency influence a job that holds consequential authority?

- **Start with:** Untrusted input, credentials, and third-party actions.
- **Prerequisites:** Understanding of triggers, jobs, and runner access.
- **Access and limits:** See the [maintained source annotation](../README.md#source-secure) for publisher context, access conditions, and the key limitation.

### [GitHub Actions: Deployment environments](https://docs.github.com/en/actions/concepts/workflows-and-actions/deployment-environments)

**Use it to answer:** Which deployment condition can the environment configuration enforce in this repository and account?

- **Start with:** The environment concept and linked configuration guidance.
- **Prerequisites:** A repository and a deployment workflow.
- **Access and limits:** See the [maintained source annotation](../README.md#source-env) for publisher context, access conditions, and the key limitation.

### [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)

**Use it to answer:** Which observable boundary separates the current symptom from the competing failure explanations?

- **Start with:** The guide matching the failing application boundary.
- **Prerequisites:** Workload, Service, and namespace familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-debug) for publisher context, access conditions, and the key limitation.

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

**Use it to answer:** Which policy layers determine whether the execution identity can perform the requested action?

- **Start with:** Policy types and the linked evaluation guidance.
- **Prerequisites:** AWS identities, resources, and basic JSON familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-iam) for publisher context, access conditions, and the key limitation.

## Apply the reading

Review an existing workflow without changing it. Identify the source trigger, executor identity, artifact reference, destination, and acceptance evidence. Note any authority that the configuration does not make clear.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

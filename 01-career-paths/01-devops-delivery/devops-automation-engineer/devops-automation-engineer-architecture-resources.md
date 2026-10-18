# DevOps Automation Engineer: Architecture Resources

Design automation around operation identity, state transitions, authority, and recovery. The difficult boundary is often between an external effect and the record that says it happened.

This page focuses on turning repeated engineering tasks into bounded, observable workflows with explicit inputs and failure behavior. **Question to keep in view:** What happens when an operation is retried after only part of it completed?

## On this page

- [Draw the state transitions](#draw-the-state-transitions)
- [Address duplicate and conflicting work](#address-duplicate-and-conflicting-work)
- [Separate execution authority from request authority](#separate-execution-authority-from-request-authority)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Draw the state transitions

Identify requested, validated, running, completed, failed, and ambiguous outcomes as appropriate to the operation. Define which transitions are durable and which can be retried. Cancellation may stop future work while leaving already-created resources to reconcile.

## Address duplicate and conflicting work

Use a stable request identity where the interface supports it. Decide how to detect an existing result before repeating side effects. For operations that cannot be made idempotent, define bounded compensating actions and a manual review route.

## Separate execution authority from request authority

The caller may be allowed to request a specific operation without receiving the executor credential. Validate target scope and inputs at the execution boundary. An audit trail should identify both the requester and the identity that changed the resource.

## Compare defensible alternatives

State requirements, constraints, and failure assumptions before selecting components. Compare at least two feasible options and record consequences, operating owners, and unresolved questions. Identify a specific observation that would change the decision. Use diagrams to clarify dependencies and authority, then validate the consequential behavior separately.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Architecture Decision Records](https://adr.github.io/)

**Use it to answer:** What alternatives did you consider, why did you choose this one, and when should the decision be revisited?

- **Start with:** The introductory explanation and a suitable template.
- **Prerequisites:** A decision with real alternatives and consequences.
- **Access and limits:** See the [maintained source annotation](../README.md#source-adr) for publisher context, access conditions, and the key limitation.

### [Python subprocess reference](https://docs.python.org/3/library/subprocess.html)

**Use it to answer:** How does the caller handle arguments, output, exit status, timeout, and effects that may outlive it?

- **Start with:** Frequently used arguments and security considerations.
- **Prerequisites:** Basic Python and process/exit-status knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-python) for publisher context, access conditions, and the key limitation.

### [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking)

**Use it to answer:** What evidence distinguishes a currently active operation from an abandoned lock?

- **Start with:** Lock behavior and force-unlock conditions.
- **Prerequisites:** Understanding of the selected backend and active operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-locking) for publisher context, access conditions, and the key limitation.

### [OPA policy language](https://www.openpolicyagent.org/docs/policy-language)

**Use it to answer:** What decision is evaluated from the input, and which component enforces that result?

- **Start with:** Language examples, input documents, and rule evaluation.
- **Prerequisites:** Structured data and basic authorization concepts.
- **Access and limits:** See the [maintained source annotation](../README.md#source-opa) for publisher context, access conditions, and the key limitation.

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

**Use it to answer:** Can untrusted input or a dependency influence a job that holds consequential authority?

- **Start with:** Untrusted input, credentials, and third-party actions.
- **Prerequisites:** Understanding of triggers, jobs, and runner access.
- **Access and limits:** See the [maintained source annotation](../README.md#source-secure) for publisher context, access conditions, and the key limitation.

## Apply the reading

Document a timeout occurring after resource creation but before status persistence. Compare checking external state, retrying the whole workflow, and manual reconciliation. State which evidence makes each option acceptable.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

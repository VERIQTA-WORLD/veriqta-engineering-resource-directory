# DevOps Consultant: Production Practice Resources

Find resources for conducting a consulting engagement around live services without blurring assessment, authorization, implementation, and acceptance.

This page focuses on assessing delivery constraints, testing improvement hypotheses, and transferring usable capabilities to client teams. **Question to keep in view:** Which change addresses the demonstrated constraint, and what evidence would show it helped?

## On this page

- [Separate discovery from execution](#separate-discovery-from-execution)
- [Evaluate the intervention with context](#evaluate-the-intervention-with-context)
- [Close access and handover deliberately](#close-access-and-handover-deliberately)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Separate discovery from execution

Document read access, test permissions, change approval, and incident responsibilities. Use client-approved paths for data and credentials. If discovery identifies an urgent problem, escalate through the agreed owner rather than assuming authority to repair it.

## Evaluate the intervention with context

Compare representative periods and account for demand, incident load, team changes, and release mix. A short pilot can establish local feasibility without proving sustained organization-wide improvement. Report the limits alongside the outcome.

## Close access and handover deliberately

Confirm operating ownership, outstanding risks, support arrangements, and removal of temporary credentials or integrations. Transfer runbooks and source material in the client's supported location. List unfinished work with a named owner rather than hiding it in a final presentation.

## Apply guidance through an operating boundary

Start with the affected service, owner, current state, and authorized task. Establish a baseline and relevant acceptance evidence. Check data, identity, capacity, and recovery implications before proposing a change. After execution, verify the user or consumer outcome and any persistent side effects rather than relying only on a successful command.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Incident Response](https://sre.google/workbook/incident-response/)

**Use it to answer:** Who coordinates response, preserves the timeline, and verifies that the affected service has recovered?

- **Start with:** Coordination, roles, communication, and follow-up.
- **Prerequisites:** Understanding of service ownership and operational impact.
- **Access and limits:** See the [maintained source annotation](../README.md#source-incident) for publisher context, access conditions, and the key limitation.

### [DORA: Software delivery performance metrics](https://dora.dev/guides/dora-metrics/)

**Use it to answer:** Which event definitions and service boundaries make a delivery measurement interpretable?

- **Start with:** Definitions and measurement boundaries.
- **Prerequisites:** A service boundary and accessible change records.
- **Access and limits:** See the [maintained source annotation](../README.md#source-metrics) for publisher context, access conditions, and the key limitation.

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

**Use it to answer:** Which user behavior should be measured, what target matters, and how will the result inform a decision?

- **Start with:** Selecting indicators, targets, and the improvement process.
- **Prerequisites:** Understanding of user-visible service behavior.
- **Access and limits:** See the [maintained source annotation](../README.md#source-slo) for publisher context, access conditions, and the key limitation.

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

**Use it to answer:** Can untrusted input or a dependency influence a job that holds consequential authority?

- **Start with:** Untrusted input, credentials, and third-party actions.
- **Prerequisites:** Understanding of triggers, jobs, and runner access.
- **Access and limits:** See the [maintained source annotation](../README.md#source-secure) for publisher context, access conditions, and the key limitation.

### [FinOps Framework](https://www.finops.org/framework/)

**Use it to answer:** Which cost is attributable to this capability, and what value or reliability requirement justifies it?

- **Start with:** Scope, allocation, ownership, and improvement capabilities.
- **Prerequisites:** Access to relevant usage, ownership, and billing context.
- **Access and limits:** See the [maintained source annotation](../README.md#source-finops) for publisher context, access conditions, and the key limitation.

## Apply the reading

Write a pilot closure note containing observed results, sampling limits, unresolved risks, acceptance status, operating owner, and access-removal evidence. Distinguish implemented changes from recommendations.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

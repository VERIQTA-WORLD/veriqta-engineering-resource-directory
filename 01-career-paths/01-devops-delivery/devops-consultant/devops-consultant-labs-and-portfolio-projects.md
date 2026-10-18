# DevOps Consultant: Labs and Portfolio Projects

Use these projects to produce evidence relevant to assessing delivery constraints, testing improvement hypotheses, and transferring usable capabilities to client teams. Each is an original project brief assembled around maintained source instructions. It is not a claim that a complete ready-made tutorial exists for every extension below.

## Before you start

Choose one project and read its full source prerequisites, permissions, access requirements, and cleanup instructions. Record versions and dedicated resource names. Use synthetic data and owned lab resources. A design-only project is valid when deployment is impractical; retain assumptions and validation plans instead of invented runtime results.

## Project 1: Assess a synthetic delivery stream

**Problem:** Create fictional change records containing active work, waiting, rework, and release verification.

**Deliverable:** Produce an evidence register, a change-path map, two competing hypotheses, and a prioritized pilot recommendation.

**Prerequisites and access:** A spreadsheet or document editor is enough. Use fictional organizations and label all records synthetic.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Remove one important data field and explain how it limits your conclusion. Change the release mix and revisit the comparison.

**Cleanup:** Delete any temporary datasets containing private material if you adapted the exercise. Synthetic portfolio records can remain with clear labeling.

**Scope limit:** A synthetic assessment demonstrates method, not a real client improvement or business result.

### Implementation resources

### [DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)

**Use it to answer:** Which technical practice or organizational dependency prevents a change from being released safely on demand?

- **Start with:** Implementing continuous delivery and common pitfalls.
- **Prerequisites:** Familiarity with a software change moving through a team.
- **Access and limits:** See the [maintained source annotation](../README.md#source-dora) for publisher context, access conditions, and the key limitation.

### [DORA: Software delivery performance metrics](https://dora.dev/guides/dora-metrics/)

**Use it to answer:** Which event definitions and service boundaries make a delivery measurement interpretable?

- **Start with:** Definitions and measurement boundaries.
- **Prerequisites:** A service boundary and accessible change records.
- **Access and limits:** See the [maintained source annotation](../README.md#source-metrics) for publisher context, access conditions, and the key limitation.

### [arc42](https://arc42.org/)

**Use it to answer:** Which quality requirement, interface, or operating risk is missing from the current design explanation?

- **Start with:** The template overview and quality requirements.
- **Prerequisites:** An identifiable system boundary and stakeholders.
- **Access and limits:** See the [maintained source annotation](../README.md#source-arc) for publisher context, access conditions, and the key limitation.

## Project 2: Compare a platform request with a smaller intervention

**Problem:** A fictional sponsor wants a portal while developers report slow access and repeated environment repairs.

**Deliverable:** Produce a discovery brief, alternatives, total ownership considerations, a pilot, and a stop-or-expand decision.

**Prerequisites and access:** Design-only work needs no accounts. If you prototype, use synthetic repositories and integrations.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Assume the available operating capacity is halved. Explain which option remains feasible and what scope you would reduce.

**Cleanup:** Remove optional prototype resources and credentials. Retain assumptions, source attribution, and the decision history.

**Scope limit:** Do not label stakeholder assumptions as research findings or present the hypothetical benefit as measured.

### Implementation resources

### [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)

**Use it to answer:** Which supported capability helps the consumer complete a task, and who will operate it?

- **Start with:** Platform capabilities and the platform-as-product discussion.
- **Prerequisites:** Experience with developer workflows and operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-platforms) for publisher context, access conditions, and the key limitation.

### [Architecture Decision Records](https://adr.github.io/)

**Use it to answer:** What alternatives did you consider, why did you choose this one, and when should the decision be revisited?

- **Start with:** The introductory explanation and a suitable template.
- **Prerequisites:** A decision with real alternatives and consequences.
- **Access and limits:** See the [maintained source annotation](../README.md#source-adr) for publisher context, access conditions, and the key limitation.

### [FinOps Framework](https://www.finops.org/framework/)

**Use it to answer:** Which cost is attributable to this capability, and what value or reliability requirement justifies it?

- **Start with:** Scope, allocation, ownership, and improvement capabilities.
- **Prerequisites:** Access to relevant usage, ownership, and billing context.
- **Access and limits:** See the [maintained source annotation](../README.md#source-finops) for publisher context, access conditions, and the key limitation.

## Project 3: Demonstrate an accepted handover

**Problem:** Use a small disposable workflow as the subject of a consulting-style handover.

**Deliverable:** Write installation and support notes, access requirements, a failure exercise, acceptance checks, and an outstanding-risk record.

**Prerequisites and access:** You need an owned test repository, appropriate runner access, and a second reviewer if available. A solo self-review must be labeled as such.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Have the reviewer diagnose a deliberately invalid configuration using only the handover material. Record where assistance was still needed.

**Cleanup:** Remove temporary access and scheduled execution. Confirm who owns any retained repository and integration.

**Scope limit:** A successful handover exercise covers this workflow and reviewer; it does not prove organization-wide adoption.

### Implementation resources

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

### [Incident Response](https://sre.google/workbook/incident-response/)

**Use it to answer:** Who coordinates response, preserves the timeline, and verifies that the affected service has recovered?

- **Start with:** Coordination, roles, communication, and follow-up.
- **Prerequisites:** Understanding of service ownership and operational impact.
- **Access and limits:** See the [maintained source annotation](../README.md#source-incident) for publisher context, access conditions, and the key limitation.

## Portfolio evidence and acceptance

| Item | What to include |
| --- | --- |
| Goal | The engineering problem and the user or operator it affects |
| Architecture | Components, dependencies, trust boundaries, and ownership |
| Reproduction | Source instructions, your additions, versions, and access needs |
| Observation | Expected and actual results with relevant context |
| Failure | The bounded fault or design challenge and your reasoning |
| Verification | Evidence that the stated outcome was achieved, or a clear untested status |
| Cleanup | Removed resources, retained resources, credentials, and outstanding costs |
| Attribution | Which implementation material came from external sources |

A passing demonstration supports the stated exercise outcome. Broader security, performance, resilience, and production-readiness claims need their own defined criteria and evidence. If a second person cannot reproduce the result, identify missing prerequisites before expanding scope.

## Sources and review scope

Prepared for VERIQTA on 18 October 2026. The linked primary-source entry pages were opened and reviewed for identity, scope, and the navigation supporting this selection. Full manuals, linked courses, and downstream examples were not reviewed in their entirety. No exercises or production changes were executed for this collection. Examples, project briefs, and decision aids are original VERIQTA editorial guidance. Use the applicable product version; access and hosted-service conditions can change.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

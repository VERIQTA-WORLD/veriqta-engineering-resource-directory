# DevOps Platform Engineer: Labs and Portfolio Projects

Use these projects to produce evidence relevant to providing supported delivery capabilities that other engineers can use through predictable interfaces. Each is an original project brief assembled around maintained source instructions. It is not a claim that a complete ready-made tutorial exists for every extension below.

## Before you start

Choose one project and read its full source prerequisites, permissions, access requirements, and cleanup instructions. Record versions and dedicated resource names. Use synthetic data and owned lab resources. A design-only project is valid when deployment is impractical; retain assumptions and validation plans instead of invented runtime results.

## Project 1: Define a supported onboarding contract

**Problem:** Choose one fictional developer team and one routine onboarding task.

**Deliverable:** Produce a user journey, contract, responsibility table, supported inputs, failure states, and consumer acceptance checks.

**Prerequisites and access:** A design-only exercise needs no portal or cloud account. Use synthetic teams, services, and identities.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Assume artifact generation succeeds but downstream authorization fails. Define status, ownership, and reconciliation without hiding partial work.

**Cleanup:** Remove optional prototypes and credentials. Retain the contract and its unresolved validation questions.

**Scope limit:** A design review does not establish usability; a consumer trial and implementation evidence are separate work.

### Implementation resources

### [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)

**Use it to answer:** Which supported capability helps the consumer complete a task, and who will operate it?

- **Start with:** Platform capabilities and the platform-as-product discussion.
- **Prerequisites:** Experience with developer workflows and operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-platforms) for publisher context, access conditions, and the key limitation.

### [C4 model](https://c4model.com/)

**Use it to answer:** Which people, systems, and execution boundaries must the audience understand before reviewing the design?

- **Start with:** System context, then container diagrams when more detail is needed.
- **Prerequisites:** Knowledge of the system and its dependencies.
- **Access and limits:** See the [maintained source annotation](../README.md#source-c4) for publisher context, access conditions, and the key limitation.

### [Architecture Decision Records](https://adr.github.io/)

**Use it to answer:** What alternatives did you consider, why did you choose this one, and when should the decision be revisited?

- **Start with:** The introductory explanation and a suitable template.
- **Prerequisites:** A decision with real alternatives and consequences.
- **Access and limits:** See the [maintained source annotation](../README.md#source-adr) for publisher context, access conditions, and the key limitation.

## Project 2: Connect catalog metadata to a template

**Problem:** Explore one catalog entity and a small template in a local Backstage learning environment.

**Deliverable:** Record service ownership metadata, input validation, generated artifacts, action authority, and the expected consumer result.

**Prerequisites and access:** Use the prerequisites and installation guidance linked from current Backstage documentation. External actions need explicitly configured integrations.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Use only synthetic destinations. Test an invalid owner or missing input and record how the user and operator discover the issue.

**Cleanup:** Stop local services and remove dedicated generated artifacts. Revoke test integration credentials and remove any generated external repositories.

**Scope limit:** Catalog ownership metadata alone does not grant or restrict external execution authority.

### Implementation resources

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

### [Backstage authentication](https://backstage.io/docs/auth/)

**Use it to answer:** How is a signed-in person mapped to the identity used by the rest of the platform?

- **Start with:** Authentication architecture and your selected provider.
- **Prerequisites:** Identity-provider and backend configuration familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-auth) for publisher context, access conditions, and the key limitation.

## Project 3: Test a permission boundary and workflow upgrade

**Problem:** Design two consumers with different authority to request a shared delivery operation.

**Deliverable:** Produce an allow/deny matrix, enforcement map, versioned workflow contract, compatibility examples, and upgrade communication.

**Prerequisites and access:** Begin design-only. An implementation needs a disposable repository or local platform with compatible permission integration.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Test a denied request and an interrupted authorized action. Then change one output contract and assess existing consumers.

**Cleanup:** Remove test identities, credentials, triggers, and dedicated resources. Preserve sanitized denied and allowed observations separately.

**Scope limit:** Passing one permission test does not prove every plugin or downstream integration enforces the same boundary.

### Implementation resources

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

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

**Use it to answer:** Can untrusted input or a dependency influence a job that holds consequential authority?

- **Start with:** Untrusted input, credentials, and third-party actions.
- **Prerequisites:** Understanding of triggers, jobs, and runner access.
- **Access and limits:** See the [maintained source annotation](../README.md#source-secure) for publisher context, access conditions, and the key limitation.

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

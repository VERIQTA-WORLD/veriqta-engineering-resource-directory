# DevOps Architect: Labs and Portfolio Projects

Use these projects to produce evidence relevant to designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership. Each is an original project brief assembled around maintained source instructions. It is not a claim that a complete ready-made tutorial exists for every extension below.

## Before you start

Choose one project and read its full source prerequisites, permissions, access requirements, and cleanup instructions. Record versions and dedicated resource names. Use synthetic data and owned lab resources. A design-only project is valid when deployment is impractical; retain assumptions and validation plans instead of invented runtime results.

## Project 1: Compare two delivery architectures

**Problem:** A fictional company needs a delivery path for three services with different release schedules. Compare independent repository workflows with a shared delivery service.

**Deliverable:** Produce context and execution views, a trust-boundary table, and two decision records. Choose a preferred option using operator capacity, recovery, and compatibility requirements.

**Prerequisites and access:** A design-only exercise needs a document editor and no cloud account. If you build a prototype, use only synthetic repositories and a dedicated lab environment.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Review an unavailable registry, an expired executor credential, and a data-incompatible rollback. State the evidence you need before committing to the design.

**Cleanup:** Retain the design and assumptions. Remove only prototype resources you actually created and revoke any disposable tokens.

**Scope limit:** A comparison can establish reasoning quality; it does not demonstrate runtime availability.

### Implementation resources

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

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

## Project 2: Validate a local delivery boundary

**Problem:** Build a disposable Kubernetes learning environment and examine how Git-controlled application configuration reaches it. Use the upstream quick starts for implementation.

**Deliverable:** Record repository identity, reconciler authority, target scope, application verification, and an intentional configuration difference.

**Prerequisites and access:** You need a supported runtime, adequate local capacity, Kubernetes tools, and compatible Argo CD instructions. Git hosting or registry actions may require accounts.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** In the dedicated lab, compare configuration drift with an intentionally invalid desired configuration. Explain how each appears to the controller and to the application user.

**Cleanup:** Remove the application and dedicated controller or cluster using the applicable upstream instructions. Remove exercise integrations and credentials separately.

**Scope limit:** A local cluster does not reproduce production control-plane availability or cloud network behavior.

### Implementation resources

### [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/)

**Use it to answer:** Which local cluster setup can reproduce the behavior of interest, and which production assumptions remain absent?

- **Start with:** Installation, creating a cluster, interacting with it, and deletion.
- **Prerequisites:** A supported container runtime, local capacity, and compatible tools.
- **Access and limits:** See the [maintained source annotation](../README.md#source-kind) for publisher context, access conditions, and the key limitation.

### [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/)

**Use it to answer:** Which desired state is authoritative, what can the reconciler change, and how is disagreement exposed?

- **Start with:** Core concepts, then the relevant user guide.
- **Prerequisites:** Kubernetes resources, Git, and application deployment knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-argo) for publisher context, access conditions, and the key limitation.

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

**Use it to answer:** Can untrusted input or a dependency influence a job that holds consequential authority?

- **Start with:** Untrusted input, credentials, and third-party actions.
- **Prerequisites:** Understanding of triggers, jobs, and runner access.
- **Access and limits:** See the [maintained source annotation](../README.md#source-secure) for publisher context, access conditions, and the key limitation.

## Project 3: Review recovery dependencies

**Problem:** Create a design review for a service whose deployment runner depends on the same environment it must recover.

**Deliverable:** Produce a dependency map, recovery access plan, data-recovery assumptions, and an acceptance checklist for a future restore test.

**Prerequisites and access:** Design-only work is suitable; use synthetic identities and architecture. Deploying a cloud test requires a dedicated account, explicit permissions, and cost controls.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Walk through runner loss, inaccessible infrastructure state, and unavailable normal identity. Identify which recovery step cannot currently be performed.

**Cleanup:** Remove any optional lab infrastructure and revoke temporary access. Record unresolved dependencies instead of inventing restore results.

**Scope limit:** A tabletop review identifies gaps but does not measure actual recovery time.

### Implementation resources

### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

**Use it to answer:** Which workload assumption needs review across reliability, security, operations, performance, cost, or sustainability?

- **Start with:** The framework overview and the pillar relevant to your review.
- **Prerequisites:** A defined workload and stakeholder requirements.
- **Access and limits:** See the [maintained source annotation](../README.md#source-aws) for publisher context, access conditions, and the key limitation.

### [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)

**Use it to answer:** Which reliability responsibility needs better evidence, ownership, or an operating procedure?

- **Start with:** The chapter corresponding to your current service concern.
- **Prerequisites:** Experience operating a service.
- **Access and limits:** See the [maintained source annotation](../README.md#source-sre) for publisher context, access conditions, and the key limitation.

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

**Use it to answer:** Which policy layers determine whether the execution identity can perform the requested action?

- **Start with:** Policy types and the linked evaluation guidance.
- **Prerequisites:** AWS identities, resources, and basic JSON familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-iam) for publisher context, access conditions, and the key limitation.

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

# DevOps Infrastructure Engineer: Labs and Portfolio Projects

Use these projects to produce evidence relevant to building and maintaining the compute, networking, identity, configuration, and state foundations behind software delivery. Each brief defines what you will build or design, the references you will use, and the evidence you should retain.

## Before you start

Choose one project and read its full source prerequisites, permissions, access requirements, and cleanup instructions. Record versions and dedicated resource names. Use synthetic data and owned lab resources. A design-only project is valid when deployment is impractical; retain assumptions and validation plans instead of invented runtime results.

## Project 1: Inspect a local infrastructure lifecycle

**Problem:** Use the Terraform Docker learning path to observe definitions, state, runtime resources, and teardown.

**Deliverable:** Retain version information, proposed and observed changes, resource identity, state handling notes, and cleanup verification.

**Prerequisites and access:** Install the versions and provider prerequisites required by the current tutorial. Use a dedicated working directory and disposable containers.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Change one controlled resource outside the declared configuration and inspect the resulting difference. Do not edit state to force an expected answer.

**Cleanup:** Follow the tutorial's destroy sequence, then check for remaining dedicated runtime resources and sensitive state copies.

**Scope limit:** Local Docker exercises do not establish shared backend locking, cloud permissions, or data restore behavior.

### Implementation resources

### [Terraform Docker tutorial collection](https://developer.hashicorp.com/terraform/tutorials/docker-get-started)

**Use it to answer:** How do definitions, state, runtime resources, and teardown relate in a small local lifecycle?

- **Start with:** Prerequisites, infrastructure lifecycle, and destroy instructions.
- **Prerequisites:** Terraform, Docker, and a suitable local machine.
- **Access and limits:** See the [maintained source annotation](../README.md#source-tf-lab) for publisher context, access conditions, and the key limitation.

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests)

**Use it to answer:** Does this test inspect a plan, execute changes, or substitute mocked behavior, and what can it prove?

- **Start with:** Test files, run blocks, and assertions.
- **Prerequisites:** Compatible Terraform version and provider prerequisites.
- **Access and limits:** See the [maintained source annotation](../README.md#source-tests) for publisher context, access conditions, and the key limitation.

## Project 2: Coordinate a shared-state design

**Problem:** Design a change path for two operators using shared infrastructure state.

**Deliverable:** Produce the backend requirements, identity boundaries, concurrency protocol, interrupted-operation runbook, and state recovery plan.

**Prerequisites and access:** Design-only work is suitable. Any backend test needs a dedicated state scope and no shared production resources.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Walk through a lock error with an operation whose completion is unknown. Define the evidence required before unlock or retry.

**Cleanup:** Remove optional backend objects only after lab resources are reconciled. Revoke test identities and preserve no exposed secrets.

**Scope limit:** A coordination design must be validated against the actual backend; support cannot be inferred from another backend.

### Implementation resources

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

## Project 3: Rebuild a configured service

**Problem:** Use a disposable host to separate resource creation, configuration, application startup, and data restoration.

**Deliverable:** Keep an ownership inventory and evidence for each lifecycle stage. Document a service-level check after the host is available.

**Prerequisites and access:** You need an authorized VM or dedicated host, compatible tools, and synthetic data. Cloud resources may incur charges.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Recreate the host while intentionally omitting one dependency, then identify the failed boundary from evidence.

**Cleanup:** Remove the dedicated host, storage, temporary identities, and optional cloud objects. Verify persistent resources separately.

**Scope limit:** Host recreation is not evidence that valuable data can be restored; test restoration independently.

### Implementation resources

### [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html)

**Use it to answer:** Which tasks preserve the desired result on repeated execution, and which have imperative side effects?

- **Start with:** Playbook execution and desired-state task structure.
- **Prerequisites:** Inventory, managed-host access, and configuration-management basics.
- **Access and limits:** See the [maintained source annotation](../README.md#source-ansible) for publisher context, access conditions, and the key limitation.

### [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html)

**Use it to answer:** What establishes startup completion and how does process behavior interact with service supervision?

- **Start with:** Service type, process startup, and restart behavior.
- **Prerequisites:** Linux service administration and the installed systemd version.
- **Access and limits:** See the [maintained source annotation](../README.md#source-systemd) for publisher context, access conditions, and the key limitation.

### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

**Use it to answer:** Which workload assumption needs review across reliability, security, operations, performance, cost, or sustainability?

- **Start with:** The framework overview and the pillar relevant to your review.
- **Prerequisites:** A defined workload and stakeholder requirements.
- **Access and limits:** See the [maintained source annotation](../README.md#source-aws) for publisher context, access conditions, and the key limitation.

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

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

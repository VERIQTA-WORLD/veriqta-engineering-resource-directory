# DevOps Automation Engineer: Labs and Portfolio Projects

Use these projects to produce evidence relevant to turning repeated engineering tasks into bounded, observable workflows with explicit inputs and failure behavior. Each brief defines what you will build or design, the references you will use, and the evidence you should retain.

## Before you start

Choose one project and read its full source prerequisites, permissions, access requirements, and cleanup instructions. Record versions and dedicated resource names. Use synthetic data and owned lab resources. A design-only project is valid when deployment is impractical; retain assumptions and validation plans instead of invented runtime results.

## Project 1: Design a resumable environment request

**Problem:** A caller loses its response after a resource is created. Design a request contract before choosing an execution engine.

**Deliverable:** Produce operation states, request identity rules, input validation, a status response, and tests for duplicate, conflicting, and interrupted requests.

**Prerequisites and access:** You can begin design-only with synthetic resource records. Any implementation needs a disposable target and no authority over shared resources.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Simulate completion of the external step before local status is recorded. Specify how the next caller discovers and reconciles the existing effect.

**Cleanup:** Remove synthetic records and dedicated resources after preserving test evidence. Do not use broad cleanup matching against a shared environment.

**Scope limit:** A local simulation does not establish the external provider's retry or consistency guarantees.

### Implementation resources

### [Python subprocess reference](https://docs.python.org/3/library/subprocess.html)

**Use it to answer:** How does the caller handle arguments, output, exit status, timeout, and effects that may outlive it?

- **Start with:** Frequently used arguments and security considerations.
- **Prerequisites:** Basic Python and process/exit-status knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-python) for publisher context, access conditions, and the key limitation.

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [Architecture Decision Records](https://adr.github.io/)

**Use it to answer:** What alternatives did you consider, why did you choose this one, and when should the decision be revisited?

- **Start with:** The introductory explanation and a suitable template.
- **Prerequisites:** A decision with real alternatives and consequences.
- **Access and limits:** See the [maintained source annotation](../README.md#source-adr) for publisher context, access conditions, and the key limitation.

## Project 2: Inspect configuration repeatability

**Problem:** Manage one harmless configuration setting on a disposable Linux VM and observe repeated execution.

**Deliverable:** Record the original setting, desired setting, first run, second run, controlled manual drift, and verified service behavior.

**Prerequisites and access:** Use a dedicated VM with compatible Ansible and explicit host access. Snapshot or rebuild capability is useful; a container may not reproduce host service behavior.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Introduce one invalid value or denied permission within the lab. Check whether the task reports failure accurately and whether partial changes remain.

**Cleanup:** Restore the original setting or delete the dedicated VM. Remove its inventory entry and test credentials.

**Scope limit:** Check mode does not prove all module behavior; record unsupported previews and actual execution separately.

### Implementation resources

### [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html)

**Use it to answer:** Which tasks preserve the desired result on repeated execution, and which have imperative side effects?

- **Start with:** Playbook execution and desired-state task structure.
- **Prerequisites:** Inventory, managed-host access, and configuration-management basics.
- **Access and limits:** See the [maintained source annotation](../README.md#source-ansible) for publisher context, access conditions, and the key limitation.

### [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html)

**Use it to answer:** Which task behavior can the preview evaluate, and which effects require another validation route?

- **Start with:** Module support and the limitations of check mode.
- **Prerequisites:** A known inventory and compatible tasks.
- **Access and limits:** See the [maintained source annotation](../README.md#source-check) for publisher context, access conditions, and the key limitation.

### [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html)

**Use it to answer:** What establishes startup completion and how does process behavior interact with service supervision?

- **Start with:** Service type, process startup, and restart behavior.
- **Prerequisites:** Linux service administration and the installed systemd version.
- **Access and limits:** See the [maintained source annotation](../README.md#source-systemd) for publisher context, access conditions, and the key limitation.

## Project 3: Publish a bounded reusable workflow

**Problem:** Expose a small validation task through a reusable workflow without giving it production credentials.

**Deliverable:** Define inputs, outputs, permissions, version references, caller examples, and representative compatibility tests.

**Prerequisites and access:** Use a disposable repository and a task that runs against synthetic files. Check runner usage and account conditions.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Submit invalid input, a failing subprocess, and a caller with insufficient permissions. Confirm that each failure produces a useful bounded result.

**Cleanup:** Disable scheduled triggers and remove test repositories or integrations if no longer needed. Preserve source and sanitized logs.

**Scope limit:** Passing local logic tests does not establish the security of every future caller or action dependency.

### Implementation resources

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

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

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

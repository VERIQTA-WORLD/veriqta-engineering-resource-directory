# DevOps Infrastructure Engineer: Tools and Technology Resources

Compare infrastructure and configuration tools by the lifecycle they own. Choose tools whose state, access, and recovery behavior you can support.

This page focuses on building and maintaining the compute, networking, identity, configuration, and state foundations behind software delivery. **Question to keep in view:** Can you change or rebuild infrastructure without losing control of state, access, data, and recovery?

## On this page

- [Separate provisioning from configuration](#separate-provisioning-from-configuration)
- [Choose backend capabilities deliberately](#choose-backend-capabilities-deliberately)
- [Include provider and upgrade work](#include-provider-and-upgrade-work)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Separate provisioning from configuration

Infrastructure tools can manage resource lifecycles, while configuration tools can manage host or service settings. Their scopes can overlap. Decide the primary owner of each setting so two controllers do not continually overwrite each other.

## Choose backend capabilities deliberately

Evaluate state access, concurrency coordination, version history, backup, and recovery for the selected backend. Backend support differs. Local experimentation is useful for learning, but a shared environment needs an explicit coordination and credential model.

## Include provider and upgrade work

Pin and review dependencies according to the environment's needs. Test changes to providers and modules against representative configurations. A small syntax change can conceal a consequential resource replacement, so inspect proposed effects and service impact.

## Compare tools against the same task

For each candidate, record the responsibility it owns, its inputs and outputs, required authority, stored state, operator burden, and failure behavior. Reject options that cannot satisfy a mandatory requirement. Compare remaining options using the same workload and team assumptions; a longer feature list is not a decision criterion by itself.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

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

### [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests)

**Use it to answer:** Does this test inspect a plan, execute changes, or substitute mocked behavior, and what can it prove?

- **Start with:** Test files, run blocks, and assertions.
- **Prerequisites:** Compatible Terraform version and provider prerequisites.
- **Access and limits:** See the [maintained source annotation](../README.md#source-tests) for publisher context, access conditions, and the key limitation.

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

## Apply the reading

Compare infrastructure-as-code plus configuration management with a machine-image approach for a small service. Identify drift, rebuild time, patch workflow, state ownership, and recovery implications.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

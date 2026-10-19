# DevOps Automation Engineer: Labs and Portfolio Projects

## Design a resumable environment request

A caller loses its response after a resource is created. Design a request contract before choosing an execution engine.

Produce operation states, request identity rules, input validation, a status response, and tests for duplicate, conflicting, and interrupted requests.

### Environment and access

You can begin design-only with synthetic resource records. Any implementation needs a disposable target and no authority over shared resources.

### Challenge the result

Simulate completion of the external step before local status is recorded. Specify how the next caller discovers and reconciles the existing effect.

A local simulation does not establish the external provider's retry or consistency guarantees.

### Cleanup

Remove synthetic records and dedicated resources after preserving test evidence. Do not use broad cleanup matching against a shared environment.

### Implementation resources

- [Python subprocess reference](https://docs.python.org/3/library/subprocess.html) · [Access and limitations](../README.md#source-python)
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Access and limitations](../README.md#source-state)
- [Architecture Decision Records](https://adr.github.io/) · [Access and limitations](../README.md#source-adr)

## Inspect configuration repeatability

Manage one harmless configuration setting on a disposable Linux VM and observe repeated execution.

Record the original setting, desired setting, first run, second run, controlled manual drift, and verified service behavior.

### Environment and access

Use a dedicated VM with compatible Ansible and explicit host access. Snapshot or rebuild capability is useful; a container may not reproduce host service behavior.

### Challenge the result

Introduce one invalid value or denied permission within the lab. Check whether the task reports failure accurately and whether partial changes remain.

Check mode does not prove all module behavior; record unsupported previews and actual execution separately.

### Cleanup

Restore the original setting or delete the dedicated VM. Remove its inventory entry and test credentials.

### Implementation resources

- [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html) · [Access and limitations](../README.md#source-ansible)
- [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) · [Access and limitations](../README.md#source-check)
- [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html) · [Access and limitations](../README.md#source-systemd)

## Publish a bounded reusable workflow

Expose a small validation task through a reusable workflow without giving it production credentials.

Define inputs, outputs, permissions, version references, caller examples, and representative compatibility tests.

### Environment and access

Use a disposable repository and a task that runs against synthetic files. Check runner usage and account conditions.

### Challenge the result

Submit invalid input, a failing subprocess, and a caller with insufficient permissions. Confirm that each failure produces a useful bounded result.

Passing local logic tests does not establish the security of every future caller or action dependency.

### Cleanup

Disable scheduled triggers and remove test repositories or integrations if no longer needed. Preserve source and sanitized logs.

### Implementation resources

- [GitHub Actions documentation](https://docs.github.com/en/actions) · [Access and limitations](../README.md#source-actions)
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) · [Access and limitations](../README.md#source-reuse)
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use) · [Access and limitations](../README.md#source-secure)

[Back to DevOps Automation Engineer resources](README.md) · [Browse this career collection](../README.md)

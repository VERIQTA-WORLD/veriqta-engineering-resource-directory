# DevOps Infrastructure Engineer: Labs and Portfolio Projects

## Inspect a local infrastructure lifecycle

Use the Terraform Docker learning path to observe definitions, state, runtime resources, and teardown.

Retain version information, proposed and observed changes, resource identity, state handling notes, and cleanup verification.

### Environment and access

Install the versions and provider prerequisites required by the current tutorial. Use a dedicated working directory and disposable containers.

### Challenge the result

Change one controlled resource outside the declared configuration and inspect the resulting difference. Do not edit state to force an expected answer.

Local Docker exercises do not establish shared backend locking, cloud permissions, or data restore behavior.

### Cleanup

Follow the tutorial's destroy sequence, then check for remaining dedicated runtime resources and sensitive state copies.

### Implementation resources

- [Terraform Docker tutorial collection](https://developer.hashicorp.com/terraform/tutorials/docker-get-started) · [Access and limitations](../README.md#source-tf-lab)
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Access and limitations](../README.md#source-state)
- [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests) · [Access and limitations](../README.md#source-tests)

## Coordinate a shared-state design

Design a change path for two operators using shared infrastructure state.

Produce the backend requirements, identity boundaries, concurrency protocol, interrupted-operation runbook, and state recovery plan.

### Environment and access

Design-only work is suitable. Any backend test needs a dedicated state scope and no shared production resources.

### Challenge the result

Walk through a lock error with an operation whose completion is unknown. Define the evidence required before unlock or retry.

A coordination design must be validated against the actual backend; support cannot be inferred from another backend.

### Cleanup

Remove optional backend objects only after lab resources are reconciled. Revoke test identities and preserve no exposed secrets.

### Implementation resources

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Access and limitations](../README.md#source-state)
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking) · [Access and limitations](../README.md#source-locking)
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) · [Access and limitations](../README.md#source-iam)

## Rebuild a configured service

Use a disposable host to separate resource creation, configuration, application startup, and data restoration.

Keep an ownership inventory and evidence for each lifecycle stage. Document a service-level check after the host is available.

### Environment and access

You need an authorized VM or dedicated host, compatible tools, and synthetic data. Cloud resources may incur charges.

### Challenge the result

Recreate the host while intentionally omitting one dependency, then identify the failed boundary from evidence.

Host recreation is not evidence that valuable data can be restored; test restoration independently.

### Cleanup

Remove the dedicated host, storage, temporary identities, and optional cloud objects. Verify persistent resources separately.

### Implementation resources

- [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html) · [Access and limitations](../README.md#source-ansible)
- [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html) · [Access and limitations](../README.md#source-systemd)
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) · [Access and limitations](../README.md#source-aws)

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

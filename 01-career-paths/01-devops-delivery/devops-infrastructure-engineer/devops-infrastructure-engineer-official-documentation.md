# DevOps Infrastructure Engineer: Official Documentation

Use these references to verify state, locking, permission, and configuration behavior before changing shared infrastructure. Pay attention to backend and module-specific limits.

## Resolve locking with evidence

A lock may represent an active operation or an interrupted one. Establish operator, operation identity, backend status, and external effects before considering unlock. Removing coordination without resolving the underlying state can permit conflicting changes.

## Inspect test and preview scope

Understand whether a test plans, applies, or mocks infrastructure. Check whether a preview can evaluate the relevant module. Treat both as bounded evidence and verify actual behavior in an appropriate environment before consequential changes.

## Check the complete permission path

Separate backend access, provider access, managed-host access, and application access. A provisioning failure can arise at any of these boundaries. Record which identity needs which action, then confirm that policy and organizational controls permit it.

## References to check against your configuration

- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests): Test files, run blocks, and assertions. [Access and technical limits](../README.md#source-tests).
- [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html): Module support and the limitations of check mode. [Access and technical limits](../README.md#source-check).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html): Service type, process startup, and restart behavior. [Access and technical limits](../README.md#source-systemd).

## A concrete documentation review

Review a planned infrastructure change. Map each step to its state store, identity, reference, expected side effect, and verification. Mark destructive or replacement behavior for explicit workload-owner review.

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

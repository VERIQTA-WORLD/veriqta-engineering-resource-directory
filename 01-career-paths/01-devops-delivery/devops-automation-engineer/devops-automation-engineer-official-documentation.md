# DevOps Automation Engineer: Official Documentation

Use these references to verify process, preview, retry, and state behavior before embedding a tool inside automation. Read the limitations as carefully as the successful example.

## Confirm subprocess behavior

Check how arguments, timeouts, exit codes, and output are handled in the language version you use. Avoid building commands through untrusted shell text. Identify what your timeout terminates and whether external work may continue after the local process ends.

## Treat preview as bounded evidence

A check or plan can reveal proposed changes, but its coverage depends on the tool and task. Identify unsupported behavior and side effects. Do not replace integration tests with a preview that cannot evaluate the relevant dependency.

## Verify backend and caller contracts

Inspect state-locking support and workflow permission propagation. A shared workflow can fail because the caller lacks authority even when the workflow logic is correct. Record both the execution identity and the resource-level permission requirements.

## References to check against your configuration

- [Python subprocess reference](https://docs.python.org/3/library/subprocess.html): Frequently used arguments and security considerations. [Access and technical limits](../README.md#source-python).
- [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html): Module support and the limitations of check mode. [Access and technical limits](../README.md#source-check).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows): Inputs, secrets, permissions, and version references. [Access and technical limits](../README.md#source-reuse).
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use): Untrusted input, credentials, and third-party actions. [Access and technical limits](../README.md#source-secure).

## A concrete documentation review

Select three automation assumptions and locate the exact reference supporting each. Design a disposable test for unsupported preview behavior, denied access, and a dependency that completes after the caller times out.

[Back to DevOps Automation Engineer resources](README.md) · [Browse this career collection](../README.md)

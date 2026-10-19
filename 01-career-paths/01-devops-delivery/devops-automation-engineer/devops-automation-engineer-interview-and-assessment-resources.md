# DevOps Automation Engineer: Interview and Assessment Resources

These problems start where a successful demo usually ends: the caller retries, a dependency responds late, or a shared interface changes.

## Prompt: timeout after creation

An API call times out, but the target environment may exist. Explain what you can and cannot infer. Identify operation or resource identifiers you would inspect before retrying. Design the response your workflow should give the caller when completion remains uncertain.

## Prompt: repeated configuration changes

An automation job reports changed resources on every run. Describe how you would distinguish desired-state drift, a non-idempotent task, unstable input, and an inaccurate result report. Propose evidence rather than immediately suppressing the changed status.

## Prompt: reusable workflow upgrade

A workflow update needs broader permissions and changes its output format. Describe versioning, consumer testing, migration, and rollback of the shared logic. Account for external effects already created by the new version.

## What to look for in your answer

Pay particular attention to ambiguous completion. Explain how you discover existing side effects, distinguish a retry from new intent, and reconcile work when the interface cannot provide a reliable result.

## References for checking the reasoning

- [Python subprocess reference](https://docs.python.org/3/library/subprocess.html) · [Access and technical limits](../README.md#source-python)
- [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html) · [Access and technical limits](../README.md#source-ansible)
- [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) · [Access and technical limits](../README.md#source-check)
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) · [Access and technical limits](../README.md#source-reuse)
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking) · [Access and technical limits](../README.md#source-locking)

[Back to DevOps Automation Engineer resources](README.md) · [Browse this career collection](../README.md)

# DevOps Infrastructure Engineer: Tools and Technology Resources

Provisioning and configuration tools can overlap. Decide which one owns a setting before you ask them to manage it together.

## Separate provisioning from configuration

Infrastructure tools can manage resource lifecycles, while configuration tools can manage host or service settings. Their scopes can overlap. Decide the primary owner of each setting so two controllers do not continually overwrite each other.

## Choose backend capabilities deliberately

Evaluate state access, concurrency coordination, version history, backup, and recovery for the selected backend. Backend support differs. Local experimentation is useful for learning, but a shared environment needs an explicit coordination and credential model.

## Include provider and upgrade work

Pin and review dependencies according to the environment's needs. Test changes to providers and modules against representative configurations. A small syntax change can conceal a consequential resource replacement, so inspect proposed effects and service impact.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Terraform | Use it for the lifecycle of resources managed by its providers and state. | A plan can include replacement or data-affecting changes that require workload-owner review. |
| Ansible | Use it for supported configuration tasks on known targets. | Check inventory, module behavior, privileges, and repeated execution. |
| Backend coordination | Use the selected backend’s supported locking and access controls. | A stale-looking lock requires investigation; different backends do not provide identical guarantees. |

## Implementation and diagnostic references

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests): Test files, run blocks, and assertions. [Access and technical limits](../README.md#source-tests).
- [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html): Playbook execution and desired-state task structure. [Access and technical limits](../README.md#source-ansible).
- [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html): Module support and the limitations of check mode. [Access and technical limits](../README.md#source-check).

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

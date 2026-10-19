# DevOps Infrastructure Engineer: Role and Responsibility Resources

Infrastructure work needs an owner for the resource, an owner for the state, and someone who can verify the workload after a change.

## Establish resource and state ownership

Record which tool manages each resource and which team approves changes. Identify manually managed dependencies. A resource appearing in code does not establish that every relevant setting or external dependency is controlled by that code.

## Design a controlled change path

Separate proposed changes, review, execution, and post-change verification. Account for concurrent operators and long-running work. Keep authority and state access bounded to the environment; a convenient shared administrator identity hides accountability and increases impact.

## Protect persistent responsibilities

Classify data, backups, identity, network connectivity, and infrastructure state according to their recovery needs. Decide what is rebuilt, restored, or reconciled. Coordinate changes with workload owners whose acceptance checks may reveal failures that resource status does not.

## Resources behind these responsibilities

- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html): Playbook execution and desired-state task structure. [Access and technical limits](../README.md#source-ansible).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html): The framework overview and the pillar relevant to your review. [Access and technical limits](../README.md#source-aws).

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

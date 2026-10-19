# DevOps Automation Engineer: Tools and Technology Resources

Use a script for work a script can own. Add orchestration when the operation needs durable status, coordination, or a recovery process.

## Keep small tasks understandable

A local script can be sufficient for a bounded operation with simple state. Add orchestration when you need durable status, coordination, or multiple dependencies. More layers introduce additional identities, upgrades, and failure paths that must earn their cost.

## Separate declarative state from imperative work

Use infrastructure and configuration tools for the resources they manage, and understand their state and module behavior. Imperative steps may still be necessary for migrations or external actions. Record their effects rather than assuming declarative tooling makes every step repeatable.

## Choose a workflow interface

Repository events, scheduled jobs, APIs, and platform forms have different callers and trust models. Define who can start work, how inputs are validated, and how results are retrieved. Shared workflows require versioning and migration guidance for consumers.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Python process wrapper | Useful when you need explicit validation, process results, and a small interface. | A process timeout can leave an external action uncertain; define lookup and reconciliation. |
| Configuration management | Useful when modules can express the target host state and report changes. | Imperative commands inside the playbook can defeat repeatability. |
| Reusable workflow | Useful when repository consumers need a supported execution contract. | Changes to inputs, permissions, or outputs need consumer compatibility checks. |

## Implementation and diagnostic references

- [Python subprocess reference](https://docs.python.org/3/library/subprocess.html): Frequently used arguments and security considerations. [Access and technical limits](../README.md#source-python).
- [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html): Playbook execution and desired-state task structure. [Access and technical limits](../README.md#source-ansible).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows): Inputs, secrets, permissions, and version references. [Access and technical limits](../README.md#source-reuse).
- [OPA policy language](https://www.openpolicyagent.org/docs/policy-language): Language examples, input documents, and rule evaluation. [Access and technical limits](../README.md#source-opa).

[Back to DevOps Automation Engineer resources](README.md) · [Browse this career collection](../README.md)

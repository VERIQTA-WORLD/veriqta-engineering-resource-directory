# DevOps Infrastructure Engineer: Skills and Prerequisite Resources

Configuration, infrastructure state, and application data are related, but losing one does not call for the same recovery procedure as losing another.

## Understand host and network dependencies

Explain how a service starts, where configuration is read, which ports it uses, and what storage or network services it depends on. Understand the installed operating environment before treating a successful provisioning operation as a usable workload.

## Develop state and provider literacy

Read how the infrastructure tool maps configuration to managed resources. Inspect provider assumptions and backend behavior. Distinguish a configuration change, a state change, and an external manual modification; they are related but not equivalent.

## Practise permission and recovery reasoning

Identify the identity performing an action and the policy layers affecting it. Test denied operations in a disposable environment. Learn how access to state or backups may expose sensitive material even when no workload endpoint is public.

## Read at the boundary you need to understand

- [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html): Service type, process startup, and restart behavior. [Access and technical limits](../README.md#source-systemd).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [Pro Git, second edition](https://git-scm.com/book/en/v2): Git Basics, then branching and the internals relevant to your question. [Access and technical limits](../README.md#source-git).

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

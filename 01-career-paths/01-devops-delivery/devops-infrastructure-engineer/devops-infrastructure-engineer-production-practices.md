# DevOps Infrastructure Engineer: Production Practice Resources

An interrupted infrastructure change leaves two questions: what happened outside the tool, and what does its state now represent?

## Control drift and concurrent changes

Identify planned and manual modifications before execution. Investigate unexpected differences rather than accepting every proposed action. Establish who can operate on shared state and how long-running or interrupted changes are reconciled.

## Verify workload behavior after changes

Check connectivity, identity, service startup, and application functionality appropriate to the change. Infrastructure creation may succeed while a dependent service cannot authenticate or reach its data store. Agree acceptance checks with the workload owner.

## Keep recovery and cost observable

Review state access and backups, credential availability, orphaned resources, and ongoing charges. Expiring temporary capacity requires ownership and dependency checks. Document exceptions instead of allowing cleanup jobs to guess whether a resource is safe to remove.

## A lock error after an interrupted change

Suppose a pipeline disconnects while changing a shared environment. A second operator receives a state-lock error and wants to remove the lock.

First establish whether the executor is still active and which resource operations have started. Inspect the backend lock information, run identity, and external resource state. Elapsed time alone does not distinguish slow work from abandoned work.

If the operation has ended, reconcile its effects before another apply. If completion remains uncertain, preserve coordination and involve the state owner. Removing the lock can make progress appear possible while allowing two operators to act on inconsistent assumptions. After reconciliation, verify the affected workload and inspect persistent data separately.

## Operating references

- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html): Module support and the limitations of check mode. [Access and technical limits](../README.md#source-check).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html): The framework overview and the pillar relevant to your review. [Access and technical limits](../README.md#source-aws).
- [FinOps Framework](https://www.finops.org/framework/): Scope, allocation, ownership, and improvement capabilities. [Access and technical limits](../README.md#source-finops).

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

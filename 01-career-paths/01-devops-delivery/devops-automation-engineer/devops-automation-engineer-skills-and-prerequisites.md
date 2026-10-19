# DevOps Automation Engineer: Skills and Prerequisite Resources

Automation depends on details that a manual operator often handles without noticing: exit status, incomplete input, stale state, and authority.

## Understand process boundaries

Learn how an invoked program receives arguments, environment values, input, and credentials. Inspect its exit status and output separately. A parent process failing to receive a response does not necessarily mean the child operation had no effect.

## Use explicit data and validation

Define schemas or clear contracts for incoming values and results. Distinguish an omitted value from an empty value and an explicit request to remove something. Reject invalid input before creating external resources whenever possible.

## Develop state and test literacy

Practise recording progress and recovering from interruption. Test unexpected inputs, denied permissions, timeouts, and duplicate requests. Learn the limits of mocks: they can validate local control flow without proving integration behavior.

## Read at the boundary you need to understand

- [Python subprocess reference](https://docs.python.org/3/library/subprocess.html): Frequently used arguments and security considerations. [Access and technical limits](../README.md#source-python).
- [Pro Git, second edition](https://git-scm.com/book/en/v2): Git Basics, then branching and the internals relevant to your question. [Access and technical limits](../README.md#source-git).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests): Test files, run blocks, and assertions. [Access and technical limits](../README.md#source-tests).
- [OPA policy language](https://www.openpolicyagent.org/docs/policy-language): Language examples, input documents, and rule evaluation. [Access and technical limits](../README.md#source-opa).

[Back to DevOps Automation Engineer resources](README.md) · [Browse this career collection](../README.md)

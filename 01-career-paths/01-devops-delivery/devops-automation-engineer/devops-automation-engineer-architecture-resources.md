# DevOps Automation Engineer: Architecture Resources

The hardest automation failure often occurs between an external side effect and the local record that says it happened.

## Draw the state transitions

Identify requested, validated, running, completed, failed, and ambiguous outcomes as appropriate to the operation. Define which transitions are durable and which can be retried. Cancellation may stop future work while leaving already-created resources to reconcile.

## Address duplicate and conflicting work

Use a stable request identity where the interface supports it. Decide how to detect an existing result before repeating side effects. For operations that cannot be made idempotent, define bounded compensating actions and a manual review route.

## Separate execution authority from request authority

The caller may be allowed to request a specific operation without receiving the executor credential. Validate target scope and inputs at the execution boundary. An audit trail should identify both the requester and the identity that changed the resource.

## The response disappears after the side effect

In this example, request `env-42` asks for a temporary environment. The resource is created, but the worker loses its connection before persisting the completed status. The caller sees a timeout.

| Next observation | What follows |
| --- | --- |
| The external resource carries a stable request identity | Inspect ownership and configuration before reusing it |
| The resource exists but cannot be matched to the request | Stop automatic creation and reconcile the ambiguity |
| No result is visible, but creation may still be running | Inspect the active operation before repeating the side effect |

A new request attempt is not necessarily a new user intention. Design the interface so the caller can ask about `env-42` without starting another creation. If the external system cannot support a reliable lookup or idempotent request, document the operator path instead of promising exactly-once behavior.

## Design methods and implementation constraints

- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Python subprocess reference](https://docs.python.org/3/library/subprocess.html): Frequently used arguments and security considerations. [Access and technical limits](../README.md#source-python).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [OPA policy language](https://www.openpolicyagent.org/docs/policy-language): Language examples, input documents, and rule evaluation. [Access and technical limits](../README.md#source-opa).
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use): Untrusted input, credentials, and third-party actions. [Access and technical limits](../README.md#source-secure).

[Back to DevOps Automation Engineer resources](README.md) · [Browse this career collection](../README.md)

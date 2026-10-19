# DevOps Architect: Tools and Technology Resources

A pipeline engine, a reconciler, and a policy engine can all appear in the same design. Give each one a clear responsibility before comparing products.

## Compare responsibilities before products

Separate workflow execution, infrastructure lifecycle, artifact storage, application reconciliation, policy evaluation, and telemetry. One product may span several concerns, but its convenience does not erase the different trust boundaries. Identify which system is authoritative for each kind of state.

## Account for operating cost

A managed workflow service reduces some maintenance while imposing account, usage, and integration constraints. A self-managed controller offers control but introduces patching, backup, capacity, and incident work. Include human operating time in the comparison.

## Make adoption reversible where practical

Define interfaces around inputs, outputs, artifact identity, and policy decisions rather than relying on undocumented product behavior. Portability has a cost, so protect the boundaries most likely to change. Require a migration plan for shared capabilities that many teams depend on.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Workflow execution | Use a workflow engine to run the build and promotion steps you can define. | Do not give every build the authority needed by the final deployment. |
| Desired-state reconciliation | Use a reconciler when continuous comparison with an authoritative configuration is part of the requirement. | Confirm who can change desired state and which resources the controller can modify or remove. |
| Policy evaluation | Use a policy engine when a decision needs to be expressed and tested independently. | Identify the enforcement point; a correct decision that no caller enforces does not protect the boundary. |

## Implementation and diagnostic references

- [GitHub Actions documentation](https://docs.github.com/en/actions): The relevant concepts, how-to guide, and reference for your task. [Access and technical limits](../README.md#source-actions).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/): Core concepts, then the relevant user guide. [Access and technical limits](../README.md#source-argo).
- [OPA policy language](https://www.openpolicyagent.org/docs/policy-language): Language examples, input documents, and rule evaluation. [Access and technical limits](../README.md#source-opa).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).

[Back to DevOps Architect resources](README.md) · [Browse this career collection](../README.md)

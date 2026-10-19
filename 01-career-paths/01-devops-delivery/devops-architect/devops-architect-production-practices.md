# DevOps Architect: Production Practice Resources

Once teams depend on a shared delivery service, that service becomes part of the production operating model.

## Connect releases to user-visible evidence

Build success, rollout completion, and useful service behavior are distinct observations. Define which signals inform acceptance and how long they need to be observed. A canary only helps when its traffic, comparison, and failure coverage are meaningful.

## Treat recovery as a dependency problem

Reverting an application artifact may not reverse a schema change, credential rotation, or external side effect. Record compatible versions, data dependencies, and authority needed during recovery. Establish what must be restored and what can be rebuilt.

## Review the shared system itself

Delivery controllers, runners, registries, and telemetry pipelines need service ownership. Inspect failure isolation and upgrade coordination across teams. Use incidents and cost observations to revisit assumptions rather than preserving architecture decisions indefinitely.

## Operating references

- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use): Untrusted input, credentials, and third-party actions. [Access and technical limits](../README.md#source-secure).
- [FinOps Framework](https://www.finops.org/framework/): Scope, allocation, ownership, and improvement capabilities. [Access and technical limits](../README.md#source-finops).

[Back to DevOps Architect resources](README.md) · [Browse this career collection](../README.md)

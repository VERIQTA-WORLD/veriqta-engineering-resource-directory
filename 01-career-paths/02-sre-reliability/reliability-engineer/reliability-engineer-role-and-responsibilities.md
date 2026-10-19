# Reliability Engineer: Role and Responsibility Resources

Start with the useful outcome the user needs, then decide which failure risks and controls deserve attention.

## Define the reliability outcome

Start with useful user or business behavior and the period over which it matters. Agree acceptable failure, performance, and recovery conditions. Component uptime alone may miss failed transactions or delayed work that users experience as unavailable service.

## Prioritize risk with evidence

Map important failure scenarios, current controls, observed incidents, and unresolved assumptions. Compare interventions by expected effect, effort, ownership, and validation. A list of best practices does not identify which change matters most to this system.

## Connect the lifecycle

Bring design, implementation, release, operations, and retirement into the same reliability discussion. Record who owns each interface and acceptance check. Use incidents and operating observations to revise assumptions instead of treating the initial design as permanent.

## Resources behind these responsibilities

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/): Request handling, dependencies, and the relevant operating concern. [Access and technical limits](../README.md#source-service).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).
- [FinOps Framework](https://www.finops.org/framework/): Scope, allocation, ownership, and improvement capabilities. [Access and technical limits](../README.md#source-finops).

[Back to Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

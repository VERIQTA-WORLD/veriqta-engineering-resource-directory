# Reliability Engineer: Production Practice Resources

An improvement should change an observed risk or operating behavior. Closing a ticket alone does not establish that it worked.

## Operate against meaningful objectives

Connect alerts, release decisions, and capacity actions to user impact. Investigate poor indicators before changing targets. Missing telemetry, changing denominators, and unrepresentative checks can make the reported objective misleading.

## Close the improvement loop

Choose an owned reliability action after incidents or reviews, define its expected mechanism, and verify its effect. Retire obsolete controls and duplicated toil where justified. Completion of a ticket is not the same as reduced risk.

## Operating references

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/): Request handling, dependencies, and the relevant operating concern. [Access and technical limits](../README.md#source-service).
- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Site Reliability Engineer: Role and Responsibility Resources

Use software engineering to change recurring operational problems, not just to make the same response faster.

## Apply engineering to recurring uncertainty

Use service evidence to choose work that improves reliability or reduces repeated operational effort. Understand the task before automating it. Measure the maintenance and failure behavior of the new mechanism so repeated manual work is not replaced with hidden complexity.

## Connect objectives and operational decisions

Use service-level objectives and error-budget information to inform release and reliability work within an agreed policy. Make missing data and stakeholder trade-offs explicit. An objective is a decision tool rather than a decorative dashboard target.

## Support response and learning

Build actionable alerts, runbooks, escalation paths, and incident learning. Protect time for durable engineering improvements. Repeated restarts can be an appropriate mitigation while remaining evidence of an unresolved system or operating problem.

## Measure the work that remains after automation

Suppose an operator spends five minutes restarting a service six times a week. Automating the restart can remove 30 minutes of repeated execution, but the incident may still interrupt users and responders.

Record detection, diagnosis, user impact, verification, recurrence, and maintenance of the new automation. Preserve the evidence needed to investigate the underlying failure. Compare stabilizing the service with making the mitigation faster; the best order depends on impact and implementation effort.

Give the durable improvement an owner and a validation condition. A quieter on-call channel is useful only if it reflects less harmful work or better response rather than a hidden service failure.

## Resources behind these responsibilities

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [Google SRE: Eliminating Toil](https://sre.google/sre-book/eliminating-toil/): Characteristics of toil and how to identify repeated operational effort. [Access and technical limits](../README.md#source-toil).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Site Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

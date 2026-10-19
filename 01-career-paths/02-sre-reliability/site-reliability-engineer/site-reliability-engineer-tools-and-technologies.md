# Site Reliability Engineer: Tools and Technology Resources

Choose tools for a specific service or operator problem and include their maintenance burden in the decision.

## Choose tools that reduce a specific problem

Use metrics, traces, alert rules, release controls, and automation against a defined service need. Compare the new maintenance burden with the repeated work removed. A large observability stack can still leave the on-call engineer unable to identify impact.

## Make automation supportable

Use bounded authority, validation, observable results, and a reconciliation route. Test incomplete work and lost responses. Automation that restarts services without preserving evidence may reduce immediate pages while making the underlying failure harder to investigate.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Actionable alerting | Use it to identify a condition an accountable responder can act on. | More thresholds can add interruption without improving response. |
| Bounded automation | Use it to remove repeated work with a clear operation contract. | Preserve evidence and handle ambiguous completion rather than masking every symptom. |
| Incident and toil records | Use them to select durable engineering work. | Count user impact and retained maintenance as well as minutes of manual execution removed. |

## Reading behind the tool decision

- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [Google SRE: Eliminating Toil](https://sre.google/sre-book/eliminating-toil/): Characteristics of toil and how to identify repeated operational effort. [Access and technical limits](../README.md#source-toil).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Site Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

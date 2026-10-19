# Site Reliability Engineer: Architecture Resources

An operable service design needs realistic staffing, authority, release controls, and recovery dependencies.

## Design for operating ownership

Include objectives, dependencies, release controls, capacity, access, and recovery in the service review. Identify which team can respond to each failure. An architecture that assumes unavailable staffing or undocumented expertise is not operationally feasible.

## Compare toil reduction and reliability risk

Select interventions using recurrence, impact, effort, and expected mechanism. A recurring manual step may reflect a missing interface, an unstable dependency, or unclear ownership. Choose whether to simplify, automate, redesign, or retire the work.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/): Error-budget consumption and alerting trade-offs. [Access and technical limits](../README.md#source-burn).
- [Google SRE: Eliminating Toil](https://sre.google/sre-book/eliminating-toil/): Characteristics of toil and how to identify repeated operational effort. [Access and technical limits](../README.md#source-toil).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).

[Back to Site Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

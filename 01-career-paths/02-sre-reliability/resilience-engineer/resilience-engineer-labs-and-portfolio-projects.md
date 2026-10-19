# Resilience Engineer: Labs and Portfolio Projects

## Design controlled degradation

Specify a useful reduced service during a dependency outage and a staged return to normal.

### Set up the exercise

Use a fictional request path with synthetic data and explicit correctness requirements. Design-only work needs no runtime.

### Investigate the behavior

Add retries and a backlog to the scenario. Decide which work is rejected, deferred, or served through a permitted fallback.

Produce propagation and recovery maps, user consequences, data constraints, admission controls, and acceptance checks.

### Finish and clean up

Remove optional local prototypes and restore changed settings. Retain the model and unresolved validation questions.

### References for this project

- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/) · [Prerequisites and limitations](../README.md#source-cascade)
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/) · [Prerequisites and limitations](../README.md#source-overload)
- [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/) · [Prerequisites and limitations](../README.md#source-service)

## Observe post-fault recovery

Run a bounded dependency fault against a synthetic service in a dedicated local or staging environment.

### Set up the exercise

Use compatible fault tooling, strict targets, independent observation, stop conditions, scoped authority, and a recovery plan.

### Investigate the behavior

Remove the fault and inspect whether reconnection or queued work recreates pressure. Increase traffic only within the agreed boundary.

Record fault removal separately from useful-service restoration, backlog drain, and data checks. Explain remaining uncertainty.

### Finish and clean up

Remove experiment objects and dedicated resources, restore configuration, and verify that fault effects and background workload have ended.

### References for this project

- [Chaos Mesh documentation](https://chaos-mesh.org/docs/) · [Prerequisites and limitations](../README.md#source-chaos)
- [Incident Response](https://sre.google/workbook/incident-response/) · [Prerequisites and limitations](../README.md#source-incident)
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/) · [Prerequisites and limitations](../README.md#source-slo)

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

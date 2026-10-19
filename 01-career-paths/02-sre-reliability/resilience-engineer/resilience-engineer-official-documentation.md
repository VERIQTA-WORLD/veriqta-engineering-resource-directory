# Resilience Engineer: Official Documentation

Use the references below when you need to establish exact behavior for designing and validating continued operation, controlled degradation, and recovery under disruption. Match the installed version and actual configuration before interpreting an observation.

## What does the selected injected action change?

Inspect fault lifecycle, target scope, authority, stop behavior, and residual effects.

Read [Chaos Mesh documentation](https://chaos-mesh.org/docs/), starting with overview, installation, the chosen fault type, and lifecycle controls. Fault controllers can have substantial authority; target selection and stopping behavior need validation.

## What disruption is covered by workload policy?

Compare intended failure protection with the documented scope and current capacity.

Read [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/), starting with voluntary and involuntary disruption and budget limits. A disruption budget does not prevent every kind of failure or guarantee spare capacity.

## What recovery material must remain available?

For PostgreSQL, inspect backup and WAL requirements before relying on a restoration route.

Read [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html), starting with base backup prerequisites, archiving, and recovery configuration. Restore into a separate target; archived WAL availability and continuity affect recoverability.

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

# Resilience Engineer: Learning Resources

Specify the permitted degraded behavior before choosing a fallback. Then study propagation, bounded validation, and recovery material so continued operation does not sacrifice the required correctness.

## Describe degraded service

Read [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/), beginning with request handling, dependencies, and the relevant operating concern.

Identify essential actions, permitted degradation, explicit rejection, and correctness requirements.

## Model overload propagation

Read [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/), beginning with overload, feedback loops, and recovery discussion.

Trace retries, timeouts, concurrent work, and the dependency that must recover.

## Design bounded validation

Read [Chaos Mesh documentation](https://chaos-mesh.org/docs/), beginning with overview, installation, the chosen fault type, and lifecycle controls.

Write the experiment hypothesis, target, scope, stop path, and post-fault checks.

## Specify data recovery

Read [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html), beginning with base backup prerequisites, archiving, and recovery configuration.

Describe the recovery material, authority, isolated target, and evidence of usable data. Use the method only for a compatible PostgreSQL environment.

Choose a [project](resilience-engineer-labs-and-portfolio-projects.md) when you need execution evidence, or work through the [assessment scenarios](resilience-engineer-interview-and-assessment-resources.md) to apply the idea under changed conditions.

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

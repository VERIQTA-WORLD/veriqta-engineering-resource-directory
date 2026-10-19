# Chaos Engineer: Learning Resources

Understand the propagation mechanism before selecting the injected fault. Add tooling only after the hypothesis, observation, stop path, and recovery check are explicit.

## Model propagation

Read [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/), beginning with overload, feedback loops, and recovery discussion.

Draw the caller, dependency, retry, and resource-pressure paths for one bounded failure.

## Define a falsifiable experiment

Read [Chaos Mesh documentation](https://chaos-mesh.org/docs/), beginning with overview, installation, the chosen fault type, and lifecycle controls.

Write the fault, exact target, permitted duration, expected service behavior, independent observer, and stop conditions.

## Understand disruption limits

Read [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/), beginning with voluntary and involuntary disruption and budget limits.

Explain which failure class a disruption budget covers and which observations are needed for other failures.

## Design response and learning

Read [Incident Response](https://sre.google/workbook/incident-response/), beginning with coordination, roles, communication, and follow-up.

Create a timeline template and a recovery checklist. Assign an improvement owner and the evidence required before expanding scope.

Choose a [project](chaos-engineer-labs-and-portfolio-projects.md) when you need execution evidence, or work through the [assessment scenarios](chaos-engineer-interview-and-assessment-resources.md) to apply the idea under changed conditions.

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

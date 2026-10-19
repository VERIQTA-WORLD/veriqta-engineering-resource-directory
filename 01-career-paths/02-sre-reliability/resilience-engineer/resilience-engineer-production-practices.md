# Resilience Engineer: Production Practice Resources

Returning traffic too quickly can recreate overload. Recovery needs its own capacity and acceptance checks.

## Observe propagation before adding retries

Compare caller attempts, dependency completions, queue growth, and timeouts. Determine whether repeated work helps or increases pressure. Use agreed controls and record the conditions under which normal traffic may resume.

## Verify a staged return

Restore essential dependencies, validate data and service behavior, then increase exposure within the plan. Track remaining backlog and secondary failures. Record where the recovery plan depended on an unavailable person, credential, or system.

## Operating references

- [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/): Overload, feedback loops, and recovery discussion. [Access and technical limits](../README.md#source-cascade).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Chaos Mesh documentation](https://chaos-mesh.org/docs/): Overview, installation, the chosen fault type, and lifecycle controls. [Access and technical limits](../README.md#source-chaos).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Resilience Engineer resources](README.md) · [Browse this career collection](../README.md)

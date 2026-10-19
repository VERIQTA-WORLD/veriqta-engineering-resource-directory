# Cloud Reliability Engineer: Architecture Resources

Map the application path and the recovery path separately before accepting a multi-zone or multi-region design.

## Align failure domains and dependencies

Map the application path and recovery path separately. Show where zonal, regional, account, and external dependencies are shared. Compare the design against a specific loss scenario rather than counting locations.

## Validate the data route

Locate backups, encryption-key authority, replication paths, and the place where restored data will be checked. Consider deletion, corruption, and compromised credentials in addition to availability. Replicated damage can cross an otherwise well-designed availability boundary.

## Make failover a supported operation

Define trigger authority, routing changes, data checks, traffic acceptance, and return-to-normal conditions. Include a plan for avoiding conflicting writers. Model the operational burden of testing and maintaining both recovery and normal paths.

## Multi-zone runtime, single-path recovery

Suppose the application runs across two zones, but the deployment runner, backup-access identity, and configuration service all depend on one regional management path.

The runtime placement may protect against a particular zonal failure. It does not establish that you can restore data or deploy a repair when the shared management path is unavailable. Draw those recovery dependencies separately and identify which authority and artifacts remain accessible.

Compare a scoped independent recovery route with keeping more standby infrastructure. The latter may shorten provisioning while leaving the same identity problem unresolved. Validate the slowest uncertain recovery stage before committing to a recovery-time objective.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html): Application scope, policies, assessments, and supported resources. [Access and technical limits](../README.md#source-hub).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Cloud Reliability Engineer: Role and Responsibility Resources

Several availability zones can protect a workload while leaving its recovery identity, backup access, or deployment path exposed.

## Assess the workload boundary

Inventory managed services, identity, network paths, quotas, deployment control, and data dependencies. Compare their failure domains with the workload objective. The architecture of one component does not establish the recovery capability of the complete application.

## Translate recovery requirements

Define the service outcome to restore, acceptable data loss, recovery time, and the assumptions behind them. Recovery time objective and recovery point objective describe different constraints. Include authority, infrastructure availability, and data validation in the recovery route.

## Own operational evidence

Connect configuration review, capacity, monitoring, exercises, and incident learning. Assign owners for quota changes, backup access, credential availability, and restore decisions. Record whether a recovery step depends on a provider control plane being reachable.

## Resources behind these responsibilities

- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html): Application scope, policies, assessments, and supported resources. [Access and technical limits](../README.md#source-hub).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html): Experiment concepts, targets, permissions, and stop conditions. [Access and technical limits](../README.md#source-fis).
- [FinOps Framework](https://www.finops.org/framework/): Scope, allocation, ownership, and improvement capabilities. [Access and technical limits](../README.md#source-finops).

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

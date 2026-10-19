# Cloud Reliability Engineer: Skills and Prerequisite Resources

Cloud reliability requires understanding both the managed-service boundary and the application responsibilities that remain yours.

## Understand managed-service boundaries

Learn what the provider manages and what you must configure, monitor, and recover. Read service-specific behavior for the selected region and architecture. A managed service can remove host administration while leaving data, access, and application compatibility responsibilities with you.

## Reason about correlated dependencies

Trace shared identity, DNS, key access, backups, and deployment services across failure domains. A diagram with separate zones may still share the dependency needed to recover. Identify where regional or account assumptions enter the plan.

## Develop cost and quota literacy

Understand resource limits, acquisition delays, reserved capacity, and recovery-region requirements. Capacity available in normal operation may not be available after a broad incident. A low-cost standby requires a tested route to useful capacity.

## Read at the boundary you need to understand

- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html): Application scope, policies, assessments, and supported resources. [Access and technical limits](../README.md#source-hub).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html): Experiment concepts, targets, permissions, and stop conditions. [Access and technical limits](../README.md#source-fis).

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

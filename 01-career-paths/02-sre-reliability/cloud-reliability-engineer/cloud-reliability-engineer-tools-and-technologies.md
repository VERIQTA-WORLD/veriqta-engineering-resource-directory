# Cloud Reliability Engineer: Tools and Technology Resources

An assessment, a fault service, and application telemetry provide different kinds of evidence. Use each for the question it can answer.

## Use assessments for the right question

A workload assessment can reveal modeled gaps and recommendations. Compare the model with the deployed resources and external dependencies. Treat omitted components as unresolved scope rather than silently assuming the assessment covers them.

## Select observation and experiment tools

Use provider telemetry alongside application evidence. Fault services can test supported actions with scoped targets and stop conditions. Inspect permissions, current action behavior, and cost before execution in a dedicated environment.

## Compare recovery approaches

Backup restoration, warm standby, and active deployments have different cost, consistency, routing, and operating needs. Select based on the requirement and team capability. More deployed regions can add complexity without solving an identity or data dependency.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Reliability framework | Use it to organize a workload review and identify missing questions. | A reviewed recommendation is not the same as a configured and verified control. |
| Resilience assessment | Use it to examine the supported resources represented by the model. | Check omitted external dependencies and model assumptions. |
| Fault experiments | Use bounded supported actions to test a selected failure assumption. | An experiment does not cover all recovery cases, and its target and control paths need their own checks. |

## Implementation and diagnostic references

- [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html): Application scope, policies, assessments, and supported resources. [Access and technical limits](../README.md#source-hub).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html): Experiment concepts, targets, permissions, and stop conditions. [Access and technical limits](../README.md#source-fis).

## Reading behind the tool decision

- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [FinOps Framework](https://www.finops.org/framework/): Scope, allocation, ownership, and improvement capabilities. [Access and technical limits](../README.md#source-finops).

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

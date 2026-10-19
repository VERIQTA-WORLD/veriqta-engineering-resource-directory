# Cloud Reliability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for making cloud workloads dependable across managed services, identity, quotas, networking, and recovery boundaries. Match the installed version and actual configuration before interpreting an observation.

## What workload is covered by the assessment?

Compare included resource types and boundaries with the complete application dependency inventory.

Read [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html), starting with application scope, policies, assessments, and supported resources. An assessment reflects modeled resources and assumptions; it is not an executed restore.

## Which identities can perform recovery?

Inspect applicable policy layers and the authority needed at each step.

Read [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html), starting with policy types and the linked evaluation guidance. Assess all applicable policy layers; one policy document is not the complete effective permission set.

## Which failure-management requirement is satisfied?

Map the recommendation to configured behavior and a workload-level validation.

Read [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html), starting with foundations, change management, and failure management. Provider resilience does not establish end-to-end application recovery.

## Related implementation references

- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html): Experiment concepts, targets, permissions, and stop conditions. [Access and technical limits](../README.md#source-fis).

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

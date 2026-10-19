# Cloud Reliability Engineer: Labs and Portfolio Projects

## Review a workload recovery boundary

Map a fictional multi-zone workload and the shared dependencies needed for recovery.

### Set up the exercise

Use a diagram or document with synthetic services, identities, quotas, and data. A design review needs no cloud deployment.

### Investigate the behavior

Remove the shared regional control path and identify which recovery steps remain possible. Compare alternative access and data routes.

Retain application and recovery views, a dependency inventory, recovery objectives, gaps, alternatives, and a staged validation plan.

### Finish and clean up

Remove any optional prototype resources and revoke disposable access. Retain no private account or customer details in shared evidence.

### References for this project

- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) · [Prerequisites and limitations](../README.md#source-aws-rel)
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) · [Prerequisites and limitations](../README.md#source-iam)
- [Architecture Decision Records](https://adr.github.io/) · [Prerequisites and limitations](../README.md#source-adr)

## Validate an isolated recovery path

Restore a small synthetic cloud workload into a separate authorized target and verify useful behavior.

### Set up the exercise

Select the actual service-specific restore documentation before execution. You need a dedicated account or scope, synthetic data, recovery authority, and cost controls.

### Investigate the behavior

Make one normal-path dependency unavailable only within the approved lab plan. Confirm whether the intended recovery route remains usable.

Record detection and recovery stages, resource and data checks, user verification, unresolved timing assumptions, and remaining cost.

### Finish and clean up

Remove the restored target, temporary routing and identities, and disposable supporting resources. Keep any source backup according to its designated owner and retention plan.

### References for this project

- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) · [Prerequisites and limitations](../README.md#source-aws-rel)
- [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html) · [Prerequisites and limitations](../README.md#source-hub)
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) · [Prerequisites and limitations](../README.md#source-iam)

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

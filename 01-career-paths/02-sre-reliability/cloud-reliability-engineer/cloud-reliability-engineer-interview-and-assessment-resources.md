# Cloud Reliability Engineer: Interview and Assessment Resources

Each scenario asks you to identify a dependency hidden behind an apparently reassuring cloud architecture.

## Two zones share recovery authority

Explain what the multi-zone arrangement protects and what remains exposed through shared credentials, control paths, or regional services. Identify the observation needed before accepting a proposed recovery guarantee.

## The recovery region lacks capacity

Compare quota, resource availability, provisioning delay, and demand management. Explain which capacity commitment or exercise could reduce uncertainty and when a different recovery approach is justified.

## Backups exist but cannot be decrypted

Trace identity and key dependencies, backup integrity, and application validation. Explain the difference between locating a backup and demonstrating usable restoration within the required time.

## What to look for in your answer

Identify the shared dependency behind the visible redundancy. Explain which recovery stage depends on capacity, authority, keys, or control-plane access and what evidence could support the promised objective.

## References for checking the reasoning

- [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html) · [Access and technical limits](../README.md#source-hub)
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) · [Access and technical limits](../README.md#source-iam)
- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) · [Access and technical limits](../README.md#source-aws-rel)

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

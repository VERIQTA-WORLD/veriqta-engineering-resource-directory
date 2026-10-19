# Cloud Reliability Engineer: Production Practice Resources

Recovery depends on resources and authority remaining available when normal operation has already failed.

## Review control dependencies

Regularly check whether recovery identities, quotas, templates, backups, and routing controls remain usable. Test within appropriate scope after meaningful changes. A recovery document that references an unavailable integration needs an owned correction.

## Measure recovery stages

Separate detection, decision, provisioning, data restoration, application verification, and traffic return. Identify the longest uncertain stage. Compare actual exercise observations with the objectives without hiding waiting time outside the measurement boundary.

## Keep provider and application evidence together

Inspect service events and status alongside your own metrics and requests. A provider report can explain a wider event but does not establish the impact or recovery of your particular workload. Verify the user-facing outcome.

## Operating references

- [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html): Foundations, change management, and failure management. [Access and technical limits](../README.md#source-aws-rel).
- [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html): Application scope, policies, assessments, and supported resources. [Access and technical limits](../README.md#source-hub).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Cloud Reliability Engineer: Learning Resources

Map the complete workload before assessing it. Review recovery authority before planning experiments, because inaccessible credentials can invalidate an otherwise plausible recovery design.

## Inventory workload and control dependencies

Read [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html), beginning with foundations, change management, and failure management.

Map deployment, identity, data, quotas, routing, and recovery domains. Identify one shared dependency that spans the intended isolation boundary.

## Evaluate the model

Read [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html), beginning with application scope, policies, assessments, and supported resources.

Compare modeled resources with the actual workload and its external dependencies. List omitted assumptions requiring another validation route.

## Trace recovery authority

Read [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html), beginning with policy types and the linked evaluation guidance.

Explain the identity and policy layers needed to retrieve data, provision capacity, and accept traffic.

## Plan a bounded validation

Read [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html), beginning with experiment concepts, targets, permissions, and stop conditions.

Select a supported fault only after defining scope, stop controls, permissions, cost, and recovery checks.

Choose a [project](cloud-reliability-engineer-labs-and-portfolio-projects.md) when you need execution evidence, or work through the [assessment scenarios](cloud-reliability-engineer-interview-and-assessment-resources.md) to apply the idea under changed conditions.

[Back to Cloud Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

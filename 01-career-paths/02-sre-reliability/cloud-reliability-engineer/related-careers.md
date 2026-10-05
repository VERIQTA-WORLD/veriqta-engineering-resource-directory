# Cloud reliability engineer: related careers

[Career overview](README.md) · [SRE and reliability directory](../README.md)

These collections overlap in reliability concerns but emphasize different engineering boundaries. Role ownership varies by organization; use the scope descriptions to find the resources you need.

## Adjacent resource collections

| Career | Distinct emphasis and overlap | Collection status |
| --- | --- | --- |
| [Infrastructure reliability engineer](../infrastructure-reliability-engineer/README.md) | Resources for reliability of compute, hosts, provisioning, storage, networking, and infrastructure control systems. | Included in this folder. |
| [Platform reliability engineer](../platform-reliability-engineer/README.md) | Resources for keeping shared developer and runtime platforms dependable: provisioning, reconciliation, build and delivery services, artifact distribution, identity, telemetry, and recovery. | Included in this folder. |
| [Resilience engineer](../resilience-engineer/README.md) | Resources for preserving useful service during faults and recovering after disruption. | Included in this folder. |
| [Capacity engineer](../capacity-engineer/README.md) | Resources for measuring demand, identifying bottlenecks, forecasting resource needs, and validating the capacity available during normal operation and failures. | Included in this folder. |
| [Site reliability engineer](../site-reliability-engineer/README.md) | Resources for applying engineering to service operations: service objectives, observability, on-call response, incident learning, safe changes, capacity, automation, and recovery. | Included in this folder. |

## Shared references

These direct references remain useful when moving between the adjacent collections. Their inclusion does not make the roles interchangeable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Well-Architected reliability pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | Review reliability questions for cloud workload foundations, change, and recovery. | Intermediate; public provider framework. Review actual service limits and workload evidence; framework use is not certification. |
| [Azure Well-Architected reliability guidance](https://learn.microsoft.com/en-us/azure/well-architected/reliability/) | Find provider guidance for failure analysis, redundancy, recovery, and reliability review. | Intermediate; public framework. Apply to the deployed services and their documented responsibility boundaries. |
| [Google Cloud reliability framework](https://cloud.google.com/architecture/framework/reliability) | Review workload reliability principles and provider-specific design considerations. | Intermediate; public framework. Architecture guidance does not guarantee that every managed service meets your objective. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |

[Browse all 12 SRE and reliability careers](../README.md#career-collections)

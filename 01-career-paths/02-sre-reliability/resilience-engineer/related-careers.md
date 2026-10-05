# Resilience engineer: related careers

[Career overview](README.md) · [SRE and reliability directory](../README.md)

These collections overlap in reliability concerns but emphasize different engineering boundaries. Role ownership varies by organization; use the scope descriptions to find the resources you need.

## Adjacent resource collections

| Career | Distinct emphasis and overlap | Collection status |
| --- | --- | --- |
| [Chaos engineer](../chaos-engineer/README.md) | Resources for designing controlled failure experiments, collecting steady-state evidence, limiting blast radius, and validating recovery. | Included in this folder. |
| [Reliability engineer](../reliability-engineer/README.md) | Resources for assessing and improving the dependability of software systems using explicit service outcomes, failure models, design reviews, tests, and production evidence. | Included in this folder. |
| [Cloud reliability engineer](../cloud-reliability-engineer/README.md) | Resources for operating reliable cloud workloads across provider health, service limits, identity, networking, scaling, deployment, persistent data, and regional recovery. | Included in this folder. |
| [Database reliability engineer](../database-reliability-engineer/README.md) | Resources for database availability, correctness, durability, query performance, replication, maintenance, backup, and recovery. | Included in this folder. |
| [Service reliability engineer](../service-reliability-engineer/README.md) | Resources for operating an individual service or connected service boundary: user-facing outcomes, dependencies, latency, correctness, change safety, capacity, and recovery. | Included in this folder. |

## Shared references

These direct references remain useful when moving between the adjacent collections. Their inclusion does not make the roles interchangeable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html) | Compare recovery strategies and resilience considerations for AWS workloads. | Advanced; define recovery time and recovery point objectives and test the complete workload. |
| [Principles of Chaos Engineering](https://principlesofchaos.org/) | Frame experiments around a steady-state hypothesis and measured failure behavior. | Intermediate; public community principles. They do not authorize production testing or guarantee an experiment's safety. |

[Browse all 12 SRE and reliability careers](../README.md#career-collections)

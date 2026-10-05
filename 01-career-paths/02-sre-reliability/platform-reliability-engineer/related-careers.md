# Platform reliability engineer: related careers

[Career overview](README.md) · [SRE and reliability directory](../README.md)

These collections overlap in reliability concerns but emphasize different engineering boundaries. Role ownership varies by organization; use the scope descriptions to find the resources you need.

## Adjacent resource collections

| Career | Distinct emphasis and overlap | Collection status |
| --- | --- | --- |
| [Infrastructure reliability engineer](../infrastructure-reliability-engineer/README.md) | Resources for reliability of compute, hosts, provisioning, storage, networking, and infrastructure control systems. | Included in this folder. |
| [Cloud reliability engineer](../cloud-reliability-engineer/README.md) | Resources for operating reliable cloud workloads across provider health, service limits, identity, networking, scaling, deployment, persistent data, and regional recovery. | Included in this folder. |
| [Service reliability engineer](../service-reliability-engineer/README.md) | Resources for operating an individual service or connected service boundary: user-facing outcomes, dependencies, latency, correctness, change safety, capacity, and recovery. | Included in this folder. |
| [Site reliability engineer](../site-reliability-engineer/README.md) | Resources for applying engineering to service operations: service objectives, observability, on-call response, incident learning, safe changes, capacity, automation, and recovery. | Included in this folder. |
| [Resilience engineer](../resilience-engineer/README.md) | Resources for preserving useful service during faults and recovering after disruption. | Included in this folder. |

## Shared references

These direct references remain useful when moving between the adjacent collections. Their inclusion does not make the roles interchangeable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) | Review platform capabilities, organizational context, and platform thinking. | Intermediate; platform design must start with developer and operator needs. |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Backstage software catalog](https://backstage.io/docs/features/software-catalog/) | Model service ownership and metadata discovery for a developer portal. | Intermediate; public documentation. Catalog metadata is not proof that a service meets production controls. |
| [Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/) | Compare production setup considerations and operating models. | Advanced; managed services retain workload and configuration responsibilities. |
| [Reliable product launches](https://sre.google/sre-book/reliable-product-launches/) | Compare readiness review, launch coordination, and production-risk reduction. | Intermediate; public book chapter. Select checks appropriate to the service and the people who own it. |

[Browse all 12 SRE and reliability careers](../README.md#career-collections)

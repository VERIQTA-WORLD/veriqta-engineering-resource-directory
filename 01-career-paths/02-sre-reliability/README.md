# SRE and reliability resources

Reliability work covers user-visible service outcomes, the systems supporting them, and recovery when those systems fail. This directory groups resources into 12 career collections so you can find tools, documentation, design guidance, learning material, practice environments, standards, and operational references for a specific boundary.

Site reliability engineering (SRE) connects engineering with service operations. Related roles can specialize in databases, networks, cloud workloads, shared platforms, capacity, scalability, failure experiments, or resilience. Titles differ across organizations; the scope of the work is a more useful guide than the title alone.

## Find the right collection

| Your current need | Start here |
| --- | --- |
| Define service-level indicators (SLIs), service-level objectives (SLOs), error budgets, on-call practices, or incident learning | [Site reliability engineer](site-reliability-engineer/README.md) |
| Diagnose or improve an individual service and its dependencies | [Service reliability engineer](service-reliability-engineer/README.md) |
| Assess reliability claims, failure assumptions, and verification evidence across a system | [Reliability engineer](reliability-engineer/README.md) |
| Improve degraded operation, failure containment, restore capability, or disaster recovery | [Resilience engineer](resilience-engineer/README.md) |
| Design a bounded failure experiment with observations and recovery checks | [Chaos engineer](chaos-engineer/README.md) |
| Understand demand, bottlenecks, quotas, useful capacity, or failure headroom | [Capacity engineer](capacity-engineer/README.md) |
| Increase useful capacity as traffic, data, tenants, or geographic scope grow | [Scalability engineer](scalability-engineer/README.md) |
| Diagnose database waits, connections, replication, durability, or restoration | [Database reliability engineer](database-reliability-engineer/README.md) |
| Investigate DNS, routes, connectivity, packet behavior, or network changes | [Network reliability engineer](network-reliability-engineer/README.md) |
| Operate dependable hosts, compute, storage, provisioning, or infrastructure controls | [Infrastructure reliability engineer](infrastructure-reliability-engineer/README.md) |
| Operate reliable cloud workloads across provider and workload responsibilities | [Cloud reliability engineer](cloud-reliability-engineer/README.md) |
| Keep shared provisioning, build, delivery, runtime, catalog, or telemetry services reliable | [Platform reliability engineer](platform-reliability-engineer/README.md) |

## Career collections

| Career | Engineering focus |
| --- | --- |
| [Capacity engineer](capacity-engineer/README.md) | Resources for measuring demand, identifying bottlenecks, forecasting resource needs, and validating the capacity available during normal operation and failures. |
| [Chaos engineer](chaos-engineer/README.md) | Resources for designing controlled failure experiments, collecting steady-state evidence, limiting blast radius, and validating recovery. |
| [Cloud reliability engineer](cloud-reliability-engineer/README.md) | Resources for operating reliable cloud workloads across provider health, service limits, identity, networking, scaling, deployment, persistent data, and regional recovery. |
| [Database reliability engineer](database-reliability-engineer/README.md) | Resources for database availability, correctness, durability, query performance, replication, maintenance, backup, and recovery. |
| [Infrastructure reliability engineer](infrastructure-reliability-engineer/README.md) | Resources for reliability of compute, hosts, provisioning, storage, networking, and infrastructure control systems. |
| [Network reliability engineer](network-reliability-engineer/README.md) | Resources for reliable connectivity, routing, DNS, traffic distribution, service discovery, and network-dependent application behavior. |
| [Platform reliability engineer](platform-reliability-engineer/README.md) | Resources for keeping shared developer and runtime platforms dependable: provisioning, reconciliation, build and delivery services, artifact distribution, identity, telemetry, and recovery. |
| [Reliability engineer](reliability-engineer/README.md) | Resources for assessing and improving the dependability of software systems using explicit service outcomes, failure models, design reviews, tests, and production evidence. |
| [Resilience engineer](resilience-engineer/README.md) | Resources for preserving useful service during faults and recovering after disruption. |
| [Scalability engineer](scalability-engineer/README.md) | Resources for increasing useful system capacity as demand, data volume, tenants, or geographic scope grow. |
| [Service reliability engineer](service-reliability-engineer/README.md) | Resources for operating an individual service or connected service boundary: user-facing outcomes, dependencies, latency, correctness, change safety, capacity, and recovery. |
| [Site reliability engineer](site-reliability-engineer/README.md) | Resources for applying engineering to service operations: service objectives, observability, on-call response, incident learning, safe changes, capacity, automation, and recovery. |

## What each collection contains

| File | Use it to find |
| --- | --- |
| `README.md` | Scope, starting resources, coverage, and navigation. |
| `toolkit.md` | Tools and implementation options grouped by engineering task. |
| `official-documentation.md` | Focused manuals, references, and implementation guidance. |
| `reference-architectures.md` | Patterns, documented designs, engineering accounts, and decision resources. |
| `learning-resources.md` | Books, courses, tutorials, talks, and discovery collections grouped by topic. |
| `labs-and-projects.md` | Practice environments and examples with access, effects, evidence, and cleanup pointers. |
| `production-responsibilities.md` | Responsibilities connected to diagnostic, change, incident, and recovery resources. |
| `standards-and-frameworks.md` | Specifications, protocols, community principles, and review frameworks with scope distinctions. |
| `related-careers.md` | Adjacent collections and the boundaries of their overlap. |

Choose a collection by your current task, then use its topic groups and selection notes. A repeated reference can serve several useful discovery views; it is not a new resource each time. Learning material is organized for browsing, with no compulsory curriculum.

## Common terms

| Term | Meaning in these collections |
| --- | --- |
| Service-level indicator (SLI) | A defined measurement of service behavior, such as the proportion of eligible requests that complete correctly within a time budget. |
| Service-level objective (SLO) | A target for an indicator over a specified scope and measurement period. |
| Error budget | The unreliability allowed by an objective; its operating policy needs agreement about measurement, authority, and exceptions. |
| Toil | Repetitive operational work that tends to grow with service use and is a candidate for engineering improvement. |
| Recovery time objective (RTO) | A target for the time to restore the required service after disruption; it needs recovery-test evidence. |
| Recovery point objective (RPO) | A target describing how much data loss is acceptable, commonly expressed as a time window; backup and restore design must support it. |

## Access and review scope

Resource descriptions and destinations were reviewed on **5 October 2026**. Documentation indexes and publisher descriptions were reviewed for their stated scope; entire manuals, books, courses, and every item in broad discovery collections were not evaluated in full. The linked labs were not executed for this directory. Match versions and read each chosen exercise's prerequisites, permissions, cost conditions, verification, and teardown guidance before running it.

Official external destinations are provided while canonical repository resource records and IDs remain unassigned. The links between the 12 career collections are local to this folder. An occasional related-career link outside this folder uses its existing GitHub path and identifies its development status.

[VERIQTA repository](https://github.com/VERIQTA-WORLD/veriqta-engineering-resource-directory)

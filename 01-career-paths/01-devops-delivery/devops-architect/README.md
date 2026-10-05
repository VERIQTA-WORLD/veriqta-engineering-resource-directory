# DevOps architect

A DevOps architect helps an organization design and improve the system through which software changes reach users. That system includes application boundaries, source control, builds, testing, artifacts, environments, deployment, identity, observability, recovery, and the people who own each part.

The role connects technical decisions to delivery outcomes. A pipeline can execute successfully while users receive a broken service. A platform can offer many capabilities while requiring teams to wait for every routine change. The architect examines those gaps and works with the responsible teams to make delivery understandable, safe, and maintainable.

“DevOps architect” is not a standardized job title. Organizations distribute these responsibilities differently, sometimes among senior DevOps engineers, platform architects, release engineers, application architects, or reliability engineers. This folder describes a responsibility profile, not a universal job specification.

## Who this path is for

This path is intended for engineers who already understand basic application delivery and want to develop architectural judgment. It is useful to DevOps, infrastructure, cloud, platform, software, security, and reliability engineers whose work crosses team or system boundaries.

You should be able to explain a basic request path, make a version-controlled change, interpret logs, understand a build and deployment, and discuss permissions and environment configuration. You do not need expertise in every product. If these foundations are unfamiliar, use the [curriculum](curriculum.md) to identify prerequisite work before tackling the architecture exercises.

Completing the path does not establish readiness to own a complex production environment independently. That requires evidence from implementation, review, operation, and collaboration in the relevant context.

## The problem the role addresses

Delivery failures often occur between individually reasonable components. A build has an unclear relationship to the deployed artifact. A security control exists but can be bypassed through another deployment route. A release mechanism can replace application code but cannot recover an incompatible data change. A shared pipeline improves consistency but concentrates too much privilege.

The architect helps teams understand these relationships. The work begins with requirements and evidence: what needs to change, who depends on it, which constraints matter, and how the result will be demonstrated.

DORA's continuous-delivery guidance emphasizes changes to practices, processes, architecture, and skills alongside tooling. That supports assessing the whole delivery system rather than assuming a new automation product will resolve the underlying problem. See [DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/).

## Typical responsibilities

| Responsibility | Questions the architect helps answer | Useful deliverables |
| --- | --- | --- |
| Delivery assessment | Where do changes wait, fail, or require repeated manual work? | Current-state map, evidence baseline, prioritized constraints |
| Architecture and boundaries | Which components and teams must coordinate for a change? | Context diagrams, dependency map, interface decisions |
| Build and artifact design | What identifies the release, and what evidence follows it? | Artifact flow, provenance requirements, retention policy |
| Environment design | How are environments created, isolated, configured, and recovered? | Environment lifecycle and ownership model |
| Release safety | How does exposure increase, and how can harm be limited? | Promotion criteria, rollout and recovery design |
| Identity and trust | Which actor can perform each privileged action? | Trust boundaries, access model, exception process |
| Operational readiness | How will teams detect, diagnose, and recover failures? | Readiness criteria, telemetry requirements, exercises |
| Adoption and evolution | How do teams use the design and improve it? | Pilot plan, migration sequence, decision records |

These outputs need implementation evidence. A diagram or policy alone cannot prove a control is effective.

## Scope and boundaries

The architect should understand enough application behavior to reason about testability, deployability, dependencies, and data compatibility. Application teams retain responsibility for domain behavior unless the organization explicitly assigns it elsewhere.

Security specialists help define threats and validate sensitive controls. Operations and reliability teams help define service expectations and recovery behavior. Platform teams help turn shared patterns into supported capabilities. Product and business stakeholders establish constraints and acceptable tradeoffs.

An architect may implement prototypes or production changes, but should not become the only person who can deploy, interpret the design, or authorize every routine decision. Clarify authority, ownership, support, and escalation rather than relying on informal influence.

## What strong judgment looks like

A strong decision explains the constraint it addresses, compares credible alternatives, acknowledges new risks, and defines validation. It also identifies when the decision should be revisited.

For example, a shared pipeline template can reduce duplicated maintenance. It can also spread a defective template across many teams. A thoughtful design considers versioning, pilot adoption, compatibility, rollback, and the limits of centralized privileges.

Similarly, choosing microservices is not a prerequisite for good delivery. Evaluate whether the application's boundaries allow the required testing and deployment independence, and whether the organization can operate the resulting complexity. DORA's [loosely coupled teams guidance](https://dora.dev/capabilities/loosely-coupled-teams/) discusses independence and architectural context.

## Read this folder in order

| File | Purpose |
| --- | --- |
| [Curriculum](curriculum.md) | Dependency-ordered learning, exercises, evidence, and completion criteria |
| [Production responsibilities](production-responsibilities.md) | Operational ownership, review questions, scenarios, and handover |
| [Toolkit](toolkit.md) | Capability-based selection and evaluation of engineering tools |
| [Learning resources](learning-resources.md) | Annotated reading routes and ways to apply them |
| [Official documentation](official-documentation.md) | Primary references with scope and version notes |
| [Related careers](related-careers.md) | Responsibility overlap, collaboration, and transition skills |

Start with the curriculum, then use the other files when a stage calls for deeper context. These pages define a learning and responsibility framework. They do not supply a tested deployment platform or product-specific executable labs.

## Assess your progress

You should increasingly be able to trace a change from intent to deployment, identify trust and failure boundaries, defend a design against alternatives, verify assumptions in a controlled environment, and explain operational ownership. Keep evidence of revisions after feedback, not only polished final diagrams.

Related repository sections include [CI/CD](../../../03-technical-domains/08-cicd/), [architecture and system design](../../../03-technical-domains/41-architecture-system-design/), [reliability](../../../03-technical-domains/21-sre-reliability/), and [reference architectures](../../../10-reference-architectures/). Some destinations remain under development.

Continue with the [curriculum](curriculum.md), or return to [DevOps delivery careers](../).

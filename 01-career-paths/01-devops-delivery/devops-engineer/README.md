# DevOps Engineer Resource Directory

Find resources for implementing and operating the path from source changes to usable services. Use this collection to choose references for a specific knowledge gap, implementation task, operating concern, or design decision.

**The central question:** Can you trace the deployed artifact to its source and establish whether users can use it?

## Find the right collection

- **[Role and Responsibility Resources](devops-engineer-role-and-responsibilities.md):** Clarify the decisions, boundaries, and evidence behind the work.
- **[Skills and Prerequisite Resources](devops-engineer-skills-and-prerequisites.md):** Find foundations for assumptions you cannot yet explain.
- **[Tools and Technology Resources](devops-engineer-tools-and-technologies.md):** Compare implementation responsibilities and operating costs.
- **[Official Documentation](devops-engineer-official-documentation.md):** Validate behavior against primary references.
- **[Learning Resources](devops-engineer-learning-resources.md):** Build a focused reading and practice plan.
- **[Architecture Resources](devops-engineer-architecture-resources.md):** Compare options using requirements and failure assumptions.
- **[Production Practice Resources](devops-engineer-production-practices.md):** Connect changes to operating evidence and recovery.
- **[Labs and Portfolio Projects](devops-engineer-labs-and-portfolio-projects.md):** Choose original project briefs with prerequisites, evidence, and cleanup.
- **[Interview and Assessment Resources](devops-engineer-interview-and-assessment-resources.md):** Practise original scenarios and assess the reasoning in your answers.
- **[Related Career Paths](devops-engineer-related-career-paths.md):** Move to a neighboring responsibility when the question changes.

## Start from your current task

| Situation | First page | What to produce |
| --- | --- | --- |
| You are exploring the responsibility | [Role and responsibilities](devops-engineer-role-and-responsibilities.md) | A clear scope and responsibility boundary |
| You need a foundation | [Skills and prerequisites](devops-engineer-skills-and-prerequisites.md) | An explanation of the relevant mechanism |
| You need exact implementation behavior | [Official documentation](devops-engineer-official-documentation.md) | A claim supported by a version-matched reference |
| You need to choose an approach | [Architecture resources](devops-engineer-architecture-resources.md) | Alternatives compared against explicit constraints |
| You need practical evidence | [Labs and portfolio projects](devops-engineer-labs-and-portfolio-projects.md) | An observed result or an honest validation plan |

## A realistic question to work through

A pipeline is green, but checkout requests fail after deployment. The release changed application configuration and a database dependency. You need to investigate the actual request path and recover without assuming pipeline success means service health.

Start by separating observations, requirements, and assumptions. Choose one of the linked collections to resolve the most consequential uncertainty. Keep a record of the evidence behind your decision and what would change it. The scenario is illustrative and does not describe a claimed client engagement or executed incident.

## Responsibility boundary

Delivery engineering connects application and infrastructure work. Application behavior, data changes, and operational responsibilities need shared ownership rather than being delegated implicitly through a job title.

## Read according to your experience

If the mechanisms are unfamiliar, use the skills and learning pages before attempting the projects. If you already implement the systems, begin with the design or operating question you need to answer. Advanced work requires defensible reasoning about authority, state, data, and recovery; it does not require adopting every tool in the directory.

Choose a small result you can explain. Keep external implementation material attributed and distinguish source guidance from your own observations. The project pages identify prerequisites and cleanup concerns; they do not claim the exercises were executed by VERIQTA.

## Resource access and selection

This collection prioritizes primary references and freely readable material. Tool execution, hosted services, registries, cloud accounts, and some software usage have separate conditions. Review the [maintained source annotations](../README.md#primary-reference-directory) for publisher context and important limits, then inspect current upstream prerequisites before implementation.

Documentation paths using latest or stable can change. Select the release matching your environment and record the version used for practical work. A public page is not a promise of free infrastructure or a complete production implementation.

## Sources and review scope

Prepared for VERIQTA on 18 October 2026. The linked primary-source entry pages were opened and reviewed for identity, scope, and the navigation supporting this selection. Full manuals, linked courses, and downstream examples were not reviewed in their entirety. No exercises or production changes were executed for this collection. Examples, project briefs, and decision aids are original VERIQTA editorial guidance. Use the applicable product version; access and hosted-service conditions can change.

[DevOps delivery collection](../README.md) · [All career paths](../../README.md)

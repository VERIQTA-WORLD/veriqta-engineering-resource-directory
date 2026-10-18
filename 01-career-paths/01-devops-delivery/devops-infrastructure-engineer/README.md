# DevOps Infrastructure Engineer Resource Directory

Find resources for building and maintaining the compute, networking, identity, configuration, and state foundations behind software delivery. Use this collection to choose references for a specific knowledge gap, implementation task, operating concern, or design decision.

**The central question:** Can you change or rebuild infrastructure without losing control of state, access, data, and recovery?

## Find the right collection

- **[Role and Responsibility Resources](devops-infrastructure-engineer-role-and-responsibilities.md):** Clarify the decisions, boundaries, and evidence behind the work.
- **[Skills and Prerequisite Resources](devops-infrastructure-engineer-skills-and-prerequisites.md):** Find foundations for assumptions you cannot yet explain.
- **[Tools and Technology Resources](devops-infrastructure-engineer-tools-and-technologies.md):** Compare implementation responsibilities and operating costs.
- **[Official Documentation](devops-infrastructure-engineer-official-documentation.md):** Validate behavior against primary references.
- **[Learning Resources](devops-infrastructure-engineer-learning-resources.md):** Build a focused reading and practice plan.
- **[Architecture Resources](devops-infrastructure-engineer-architecture-resources.md):** Compare options using requirements and failure assumptions.
- **[Production Practice Resources](devops-infrastructure-engineer-production-practices.md):** Connect changes to operating evidence and recovery.
- **[Labs and Portfolio Projects](devops-infrastructure-engineer-labs-and-portfolio-projects.md):** Choose projects with prerequisites, evidence, and cleanup.
- **[Interview and Assessment Resources](devops-infrastructure-engineer-interview-and-assessment-resources.md):** Practise original scenarios and assess the reasoning in your answers.
- **[Related Career Paths](devops-infrastructure-engineer-related-career-paths.md):** Move to a neighboring responsibility when the question changes.

## Start from your current task

| Situation | First page | What to produce |
| --- | --- | --- |
| You are exploring the responsibility | [Role and responsibilities](devops-infrastructure-engineer-role-and-responsibilities.md) | A clear scope and responsibility boundary |
| You need a foundation | [Skills and prerequisites](devops-infrastructure-engineer-skills-and-prerequisites.md) | An explanation of the relevant mechanism |
| You need exact implementation behavior | [Official documentation](devops-infrastructure-engineer-official-documentation.md) | A claim supported by a version-matched reference |
| You need to choose an approach | [Architecture resources](devops-infrastructure-engineer-architecture-resources.md) | Alternatives compared against explicit constraints |
| You need practical evidence | [Labs and portfolio projects](devops-infrastructure-engineer-labs-and-portfolio-projects.md) | An observed result or an honest validation plan |

## A realistic question to work through

Two engineers change a shared environment while a backend lock fails. The environment also contains manual configuration and persistent data. You need a controlled infrastructure lifecycle and a credible recovery plan.

Start by separating observations, requirements, and assumptions. Choose one of the linked collections to resolve the most consequential uncertainty. Keep a record of the evidence behind your decision and what would change it.

## Responsibility boundary

Infrastructure definitions do not automatically own application migrations, data retention decisions, or service acceptance. Establish those boundaries with workload and data owners.

## Read according to your experience

If the mechanisms are unfamiliar, use the skills and learning pages before attempting the projects. If you already implement the systems, begin with the design or operating question you need to answer. Advanced work requires defensible reasoning about authority, state, data, and recovery; it does not require adopting every tool in the directory.

Choose a small result you can explain. Keep external implementation material attributed and distinguish source guidance from your own observations. Use the project pages to check prerequisites, plan cleanup, and define the evidence you will collect.

## Resource access and selection

This collection prioritizes primary references and freely readable material. Tool execution, hosted services, registries, cloud accounts, and some software usage have separate conditions. Review the [maintained source annotations](../README.md#primary-reference-directory) for publisher context and important limits, then inspect current upstream prerequisites before implementation.

Documentation paths using latest or stable can change. Select the release matching your environment and record the version used for practical work. A public page is not a promise of free infrastructure or a complete production implementation.

[DevOps delivery collection](../README.md) · [All career paths](../../README.md)

# DevOps Architect: Interview and Assessment Resources

An architecture discussion becomes interesting when the first reasonable answer stops fitting the constraints. Work through the prompts below before choosing a product.

## Prompt: shared delivery capability

Eight services use separate deployment scripts and a shared account. Ask about team ownership, release coupling, access, workload state, recovery needs, and current pain before proposing components. Explain what you would standardize first and what should remain application-specific.

## Prompt: a misleadingly successful rollout

A release passes pipeline checks and its infrastructure rollout completes, but a subset of users sees errors. Explain the missing acceptance evidence. Compare pausing, reducing exposure, reverting an artifact, and repairing forward in light of data compatibility.

## Prompt: a smaller operating team

Your preferred design requires a controller and a portal, but only one engineer can operate shared services. Reassess scope and managed alternatives. State what capability you would defer and which risk remains acceptable only with explicit stakeholder agreement.

## What to look for in your answer

Your answer should expose a design assumption, compare an implementable alternative, and identify the team that will operate the result. A detailed diagram is less convincing if the recovery authority or data compatibility remains unexplained.

## References for checking the reasoning

- [C4 model](https://c4model.com/) · [Access and technical limits](../README.md#source-c4)
- [Architecture Decision Records](https://adr.github.io/) · [Access and technical limits](../README.md#source-adr)
- [Canarying Releases](https://sre.google/workbook/canarying-releases/) · [Access and technical limits](../README.md#source-canary)
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/) · [Access and technical limits](../README.md#source-slo)
- [DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/) · [Access and technical limits](../README.md#source-dora)

[Back to DevOps Architect resources](README.md) · [Browse this career collection](../README.md)

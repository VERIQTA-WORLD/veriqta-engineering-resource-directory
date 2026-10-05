# How to use this repository

Use this directory around a question you want to answer. It is organized to connect knowledge and resources, so you can enter through a role, subject, technology, operating environment, or symptom and follow relevant relationships.

This guide is for all readers. You need no command-line setup to begin. Its examples are illustrative browsing journeys, not claims that every linked subject is already published.

## Start with a concrete goal

“I want to learn DevOps” is a useful direction, but it is too broad to determine your next step. Narrow it to something you can investigate: understand a role's responsibilities, explain how an application reaches production, or learn how to diagnose a failed release.

| Starting question | Entry point | What to look for |
| --- | --- | --- |
| What does this engineer own? | [Career paths](../01-career-paths/) | Responsibilities, progression, and adjacent roles |
| What knowledge am I missing? | [Technical domains](../03-technical-domains/) | Foundations, prerequisites, and learning outcomes |
| What technology fits this task? | [Tools](../02-tools/) | Purpose, requirements, limitations, and alternatives |
| How does this work in my cloud context? | [Cloud providers](../04-cloud-providers/) | Identity, networking, architecture, operations, and cost |
| How do these projects work together? | [Technology ecosystems](../05-technology-ecosystems/) | Component responsibilities and integrations |
| What evidence explains this failure? | [Production problems](../06-production-problems/) | Symptoms, triage, diagnostic branches, and verification |

The [repository map](repository-map.md) explains the supporting sections, including references, architectures, indexes, and contribution systems.

## Recognize what each page is meant to provide

A folder README introduces a subject and its navigation. A curriculum arranges learning outcomes in dependency order. A tool entry explains a technology's purpose and suitability. A resource record helps you assess an external reference. A troubleshooting guide connects observations to possible explanations and actions.

These are different forms of guidance. A curriculum is not a promise that every linked lesson has been completed. An architecture diagram is not proof that its design has been tested. A documentation link is not evidence that an accompanying command has run successfully.

Read status, prerequisites, version context, and verification notes wherever available. Many destinations remain under development, and some current files are empty. If essential context is absent, do not treat the page as a complete practical procedure.

## Follow a learning journey

**Illustrative example:** you want to understand application delivery before choosing pipeline tools.

1. Begin with [career selection](choose-your-career.md) if you are unsure which kind of work interests you.
2. Open the [continuous integration and continuous delivery domain](../03-technical-domains/08-cicd/) to locate the intended conceptual material.
3. Identify prerequisite gaps in [version control](../03-technical-domains/06-version-control/), [build engineering](../03-technical-domains/07-build-engineering/), or [testing](../03-technical-domains/37-testing/).
4. Use [tool selection](find-a-tool.md) to define requirements before exploring implementations.
5. Connect the learning to a production problem or architecture when relevant content becomes available.

The useful outcome is an explanation of the delivery process and its dependencies. Completing a list of product names is a weaker measure of progress.

## Follow a technology decision journey

**Illustrative example:** a team needs to collect application telemetry.

Start with the operational question: what must the team observe, and which decisions will the evidence support? Explore the [observability domain](../03-technical-domains/20-observability/) to understand the kinds of signals and their purpose. Then use the [tool guide](find-a-tool.md) to compare options against deployment, access, retention, integration, cost, and ownership requirements.

Use ecosystem material to understand component relationships. Consult official documentation for the versions being considered. Record what has been demonstrated in a controlled trial and what remains assumed.

## Follow an investigation journey

**Illustrative example:** requests become slower after a release.

Begin with [Solve a production problem](solve-a-production-problem.md). Describe the affected request, time window, and scope. Choose the problem category closest to the symptom, then follow its evidence requirements. Return to domains when a mechanism is unfamiliar and to documentation when a check depends on a particular product version.

A productive journey reduces uncertainty. Do not jump directly from a symptom to the most familiar corrective command.

## Keep a working note

Use a simple record while learning or evaluating a subject:

| Field | What to record |
| --- | --- |
| Goal | The question you intend to answer |
| Starting knowledge | What you already understand and what you need first |
| Resources | Pages and documentation that address the question |
| Findings | What you can now explain, with supporting evidence |
| Practical context | Environment, versions, permissions, and constraints |
| Gaps | Conflicting information, missing content, or untested assumptions |
| Next step | The smallest useful follow-up |

For practical work, record both success and failure observations. A failed test can teach something useful when you understand its cause and limits. Remove secrets and personal information before sharing evidence.

## Assess your progress

Ask whether you can explain the subject in your own words, identify its dependencies, interpret an example's result, describe a likely failure, and justify when an approach is appropriate. For hands-on material, also ask whether you can reproduce the result and clean up the resources safely.

If you cannot, locate the missing prerequisite or seek a more suitable explanation. Do not assume that memorizing commands establishes understanding.

## When a page is missing or incomplete

Confirm that you are in the intended folder using the [repository map](repository-map.md). Read its available README or nearby context. Record the missing topic and, if you wish to contribute, use the [contribution guide](contribution-guide.md) to describe a focused improvement.

Return to [Start Here](README.md), or choose a route through [domains](browse-by-domain.md), [cloud contexts](browse-by-cloud.md), or [careers](choose-your-career.md).

# Choose Your Starting Point in DevOps, Cloud, and Infrastructure Engineering

Choose your starting point from the work you need to do and the knowledge you already have. Job titles can help you discover responsibilities, but they do not tell you which concept you need next. Use this guide to select a manageable question, find the right collection, and decide what evidence will show progress.

## Choose by your immediate goal

| Your goal | First route | A useful result |
| --- | --- | --- |
| Understand an unfamiliar role | [Career paths](../01-career-paths/README.md) | A short list of responsibilities and the knowledge behind them |
| Develop technical foundations | [Engineering domains](../02-engineering-domains/README.md) | An explanation and a small exercise you can reproduce |
| Use a specific technology | [Tools and ecosystems](../03-tools-and-ecosystems/README.md) | A working example supported by relevant documentation |
| Work within a cloud environment | [Cloud and infrastructure](../04-cloud-and-infrastructure/README.md) | A provider-specific plan with access, cost, and cleanup considered |
| Investigate a failure | [Production problems](../05-production-problems/README.md) | Evidence that narrows plausible causes |
| Evaluate a design | [Architecture and reliability](../07-architecture-and-reliability/README.md) | Options compared against explicit requirements |
| Find an exercise or course | [Learning and practice](../06-learning-and-practice/README.md) | Material with prerequisites and an observable outcome |

Some destinations currently provide navigation rather than populated subject guides. If a linked file is empty, treat it as unfinished. Use the [external starting resources](README.md#useful-external-starting-resources) while that collection develops.

## If you are new to infrastructure engineering

Begin with the behavior of a small system you can inspect. Learn how to navigate files, understand permissions, identify a process, read its output, and explain how another program connects to it. Add version control so you can track changes. Introduce scripting when you have a repeated task worth automating.

The sequence below is a practical starting recommendation, not an admission requirement or a universal curriculum.

| Foundation | Question to investigate | Evidence to keep |
| --- | --- | --- |
| Operating systems | What does a running program depend on? | Notes identifying its configuration, permissions, logs, and dependencies |
| Networking | How does a client reach a service? | An annotated request path and observations from your own environment |
| Version control | How can you inspect and recover changes? | A disposable repository with understandable commits |
| Scripting | How can you repeat a task and detect failure? | A small script with clear inputs, outputs, and failure behavior |
| Application operation | How do you know an application is useful to its caller? | A functional check and an explanation of what it proves |

You can study these together through a small application. You do not need to complete every networking topic before using Git, or master a programming language before reading service logs.

Use [Pro Git](https://git-scm.com/book/en/v2) for version-control foundations. It is free online; start with Getting Started and Git Basics. Use a disposable local repository for practice. Platform-specific access controls and CI/CD require additional references.

## If you develop software and want to understand operations

Follow one application beyond its source code. Identify how it is built, configured, started, accessed, observed, and recovered. Investigate one stage at a time.

For a container learning goal, [Docker Get Started](https://docs.docker.com/get-started/) provides public introductory documentation and a route to its workshop. You need a suitable container environment for practical work. Check installation and licensing conditions before choosing software.

Your first useful outcome might be a documented application that another person can run. Extend it by explaining configuration, persistent data, failed startup, and cleanup. A successful local run is a foundation for further work; it does not demonstrate high availability or secure operation.

## If you administer systems and want to develop automation skills

Choose a repeated task you already understand. Document its inputs, necessary permissions, expected result, and failure cases before automating it.

Examples include checking a known service's status, collecting diagnostic information, or validating a configuration file. Start with bounded tasks whose effects you can inspect. Repeatedly running automation should have an understood result, including when the requested state already exists.

Use the [automation career category](../01-career-paths/11-automation/README.md) and [engineering domains](../02-engineering-domains/README.md) as discovery routes. Decide which concept you need before choosing a tool: structured data, error handling, desired state, scheduling, or permissions.

## If you already work in DevOps, cloud, SRE, or platform engineering

Start with the responsibility that currently costs you the most uncertainty or effort. Avoid restarting an entire beginner roadmap when you need a focused improvement.

| Current concern | Focus your research on | Useful evidence |
| --- | --- | --- |
| Releases are difficult to assess | Acceptance signals, deployment boundaries, compatibility, and rollback | A release decision supported by service behavior |
| Alerts generate little useful action | User impact, signal quality, ownership, and response | An alert whose purpose and response you can explain |
| Provisioning is inconsistent | State, dependencies, permissions, and reproducibility | A controlled change with before-and-after evidence |
| Developers wait for routine infrastructure | User needs, supported workflows, authorization, and ownership | A bounded self-service workflow with operating responsibilities |
| Recovery is uncertain | Dependencies, data restoration, objectives, and verification | An observed restore exercise in an authorized environment |

For reliability study, [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) is freely readable. Select a chapter that matches the concern you identified. Translate its examples to your own service and team rather than adopting every practice at once.

## If you need Kubernetes

First identify the Kubernetes task. Learning the workload model, deploying an application, investigating traffic, and operating a cluster are different goals.

Use the [Kubernetes documentation](https://kubernetes.io/docs/home/) to choose between concepts, tutorials, tasks, and references. It is publicly readable. Practical exercises require an appropriate environment, which may incur costs. Choose the release documentation applicable to your cluster.

Before a cluster exercise, check whether you can explain the container's startup, configuration, network listener, and persistence needs. If those are unclear, return to the relevant foundation instead of treating orchestration as a substitute for application understanding.

## If you are responding to an incident

Start with impact, scope, timing, and evidence. Write a neutral observation such as “requests to one endpoint fail after the last deployment.” Do not begin with an assumed diagnosis such as “the network is broken.”

Use the [production-problem collection](../05-production-problems/README.md) as a discovery route. Where a guide is unfinished, use documentation matching the system and version. Follow your organization's incident process and involve the appropriate service owners.

Keep a timeline of observations and changes. Prefer checks that distinguish hypotheses. A mitigation that reduces impact may be appropriate before the root cause is known; record what it changed and what remains unresolved.

## If you are preparing for an interview or portfolio review

Choose a responsibility and collect evidence that you can reason about it. A small, well-understood project can support a stronger explanation than a large installation you cannot diagnose.

Prepare to explain your requirements, alternatives, implementation, observations, failures, and limitations. Attribute reference code and guided exercises. Describe lab work as lab work and design-only work as design-only work.

## Commit to a first outcome

Complete these sentences before opening another resource:

> I want to understand or accomplish…
>
> I already know…
>
> The next gap I need to address is…
>
> I will use…
>
> I will know I have made progress when…

If you cannot define the final sentence, narrow the goal. After your first outcome, decide whether you need more foundations, implementation practice, operating experience, or a broader design perspective.

[Start Here](README.md) · [Find a resource](how-to-find-a-resource.md) · [Evaluate a resource](how-to-evaluate-an-engineering-resource.md)

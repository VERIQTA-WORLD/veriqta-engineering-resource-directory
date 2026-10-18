# How to Find the Right Engineering Resource

Find resources by the question you need to answer. A broad search for a tool often returns introductions, product pages, examples, and troubleshooting discussions together. This guide helps you narrow the task, choose a collection, and select material you can use.

## Turn your need into a searchable question

Write down four things: the task, the relevant system, the environment, and the result you need. Include the product version when behavior may differ between releases.

| Broad search | More useful question |
| --- | --- |
| Learn Kubernetes | Which references explain how a Service selects application backends? |
| Learn Terraform | Where is backend state locking documented for the backend I use? |
| Learn monitoring | Which signals would help detect failed checkout requests? |
| Learn AWS | Which identity documentation applies to this workload's access requirement? |
| Fix deployment | What changed between the last successful release and the first failing request? |

Specificity helps you reject material that shares a keyword but addresses a different problem. Keep the question open enough to investigate alternatives. Searching only for your assumed root cause can hide useful evidence.

## Choose the right collection

| What you know | Where to begin | Why |
| --- | --- | --- |
| A role or responsibility | [Career paths](../01-career-paths/README.md) | Connect responsibilities with selected subject resources |
| A concept | [Engineering domains](../02-engineering-domains/README.md) | Find foundations before implementation details |
| A product or project name | [Tools and ecosystems](../03-tools-and-ecosystems/README.md) | Locate technology-specific references |
| A provider or infrastructure type | [Cloud and infrastructure](../04-cloud-and-infrastructure/README.md) | Account for implementation and environment differences |
| An observed failure | [Production problems](../05-production-problems/README.md) | Organize evidence around symptoms |
| A practice goal | [Learning and practice](../06-learning-and-practice/README.md) | Discover material designed around exercises |
| A design requirement | [Architecture and reliability](../07-architecture-and-reliability/README.md) | Compare approaches and constraints |
| A specification or control requirement | [Standards and documentation](../08-standards-and-documentation/README.md) | Locate authoritative definitions and scope |
| A preferred format or alternative browsing route | [Resource indexes](../09-resource-indexes/README.md) | Find cross-references to maintained collections |

Several collections are still being populated. An empty file is unfinished. If your route ends there, use the external references in [Start Here](README.md#useful-external-starting-resources), then navigate within the relevant official source.

## Search the repository in layers

Start with the collection README and its subject names. If browsing does not locate the topic, use GitHub's file finder for a filename or repository-scoped code search for text. Search interfaces and indexing coverage can vary; sign-in may be required for some search features.

Try the product name first, then the mechanism or symptom. For example, a resource relevant to deployment verification may appear under release engineering, reliability, or production operations.

Useful alternate terms include:

| Term you started with | Related terms to investigate |
| --- | --- |
| CI/CD | Build, artifact, release, deployment, promotion |
| Monitoring | Metrics, logs, traces, telemetry, alerting |
| Recovery | Restore, backup, failover, disaster recovery |
| Access | Identity, authentication, authorization, permissions |
| Networking | DNS, routing, connection, proxy, endpoint |
| Automation | Scripting, provisioning, configuration, reconciliation |

These terms are related, not interchangeable. Use them to find adjacent material, then check whether it addresses your actual question.

## Match the resource format to the task

| Resource format | Best use | Check before relying on it |
| --- | --- | --- |
| Concept guide | Build a mental model | Definitions, assumed knowledge, and scope |
| Tutorial | Learn through a guided example | Prerequisites, environment, expected result, cleanup |
| Task guide | Complete a defined operation | Starting state, permissions, version, side effects |
| Reference | Confirm exact behavior or syntax | Applicability to the release and component |
| Architecture example | Study one design | Workload assumptions, ownership, cost, failure model |
| Incident report | Understand a documented event | Timeline, evidence, contributing conditions, follow-up |
| Book or course | Develop a broader subject | Edition or syllabus, depth, access, practice requirements |
| Specification | Understand a defined interface or requirement | Status, version, applicability, implementation support |

A tutorial can omit detail to keep an exercise manageable. A reference can document behavior without explaining how to learn it. You may need both.

## Follow a focused reading path

For a topic you have not used before, begin with a concept explanation. Read a small worked example next, then consult the reference when you need exact behavior. For an operating issue, begin with the observed state and the implementation reference; return to foundations when a mechanism is unclear.

The [Kubernetes documentation](https://kubernetes.io/docs/home/) illustrates these distinctions through its concepts, tutorials, tasks, and reference navigation. It is free to read. Select the release matching your environment; exercises need suitable infrastructure. The documentation home is a discovery route, not a single troubleshooting procedure.

## Worked discovery example: an unreachable application

Suppose your container starts, but you cannot reach the application from your laptop. This is an illustrative research scenario, not a diagnosis or an executed lab.

1. **State the observation.** Record the client, address, port, protocol, and actual failure. “Cannot connect” is more useful when you distinguish timeout, refusal, name-resolution failure, or an HTTP response.
2. **Identify the boundary.** Establish whether you are using a local container, a virtual machine, or a cluster. References for a different environment may introduce irrelevant steps.
3. **Find the underlying concept.** Review how the application listens and how traffic reaches that listener.
4. **Find the implementation guide.** Use documentation for the runtime and network configuration you actually use.
5. **Choose a discriminating check.** Ask what observation would distinguish application startup from exposure or reachability problems.
6. **Stop collecting unrelated material.** Once you have a suitable explanation and the relevant implementation reference, investigate before adding another tutorial.

The useful result is a smaller set of plausible explanations supported by observations. A search result that mentions the same error is only a lead until its conditions match yours.

## When you need to search beyond the directory

Use the original publisher's documentation search with the product, component, task, and version. For public web searches, combine those terms and include a distinctive error fragment when appropriate.

Remove secrets, private hostnames, customer identifiers, and sensitive log content before submitting a query to a public search engine or external tool. Search for a sanitized error pattern when exact text contains private information.

When you land on a broad catalog, follow it to the actual resource. A course-provider homepage cannot establish that a specific course covers your topic. A repository README cannot establish that every example remains compatible.

## Keep a short research record

Record your question, selected links, relevant sections, applicable version, and what you learned. Note why a promising source did not fit. This prevents repeated searching and makes later review easier.

You have found enough material to start when you can identify the applicable environment, explain the next step, and state how you will assess its result. Continue with [resource evaluation](how-to-evaluate-an-engineering-resource.md) before investing substantial time or applying consequential guidance.

## Review scope

Prepared for VERIQTA on 18 October 2026. Repository paths were checked against the current structure. The Kubernetes documentation entry page was reviewed for its discovery categories; no downstream procedure was executed. Search examples and investigation sequences are editorial guidance.

[Start Here](README.md) · [Choose your starting point](choose-your-starting-point.md) · [Evaluate a resource](how-to-evaluate-an-engineering-resource.md)

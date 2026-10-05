# DevOps architect toolkit

Build a toolkit around the capabilities needed to design, validate, and operate a delivery system. The objective is to understand what each component contributes and what responsibility it introduces, not to accumulate product names.

This guide assumes basic delivery knowledge. It defines capability and evaluation criteria rather than current product rankings, commands, licensing, or pricing. Check the official documentation for any implementation and version you select.

## Map capabilities to responsibilities

| Capability | Why it matters | What to evaluate |
| --- | --- | --- |
| Version control and review | Records source and configuration changes | Review boundaries, access, history, emergency routes, and ownership |
| Build execution | Converts inputs into candidate outputs | Worker isolation, dependencies, repeatability, queues, and credentials |
| Automated verification | Supplies evidence for change decisions | Test reliability, relevance, feedback time, false results, and maintenance |
| Artifact storage | Preserves identifiable release outputs | Immutable identity, access, retention, recovery, and promotion |
| Infrastructure management | Creates and changes operating resources | State, drift, permissions, concurrency, recovery, and shared resources |
| Configuration and secrets | Supplies environment-specific information | Validation, scope, rotation, exposure, and runtime access |
| Deployment orchestration | Changes the running system | Ordering, convergence, failure handling, partial updates, and status |
| Release exposure | Controls which users receive changed behavior | Evaluation, rollback limitations, traffic representativeness, and ownership |
| Observability | Supports release and incident decisions | Signal quality, version attribution, access, retention, and missing evidence |
| Supply-chain assurance | Relates artifacts to expected production processes | Provenance generation, authenticity, verification, and rejection behavior |
| Policy enforcement | Implements agreed change and access constraints | Bypass routes, exceptions, evidence, usability, and failure modes |
| Documentation and architecture modeling | Makes decisions and boundaries understandable | Versioning, discoverability, audience, and connection to implementation |

A product may provide several capabilities. An integrated suite can reduce some coordination but can also concentrate dependency and access risks. Separate products can offer flexibility while increasing integration and operational effort. Evaluate the actual arrangement.

## Use requirement-driven selection

Write a requirement in terms of the outcome. For example, “deployment must use the candidate that passed verification” is more useful than “we need a registry.” Decide how the outcome will be demonstrated, then compare implementations.

Assess deployment context, interfaces, scale, security, availability, support skills, data handling, operating effort, and exit options. Identify hard constraints before comparing convenience features. Record what is measured, what is documented, and what remains assumed.

Use the repository's [tool selection guide](../../../00-start-here/find-a-tool.md) for a reusable decision framework. Browse [CI/CD tools](../../../02-tools/cicd/), [infrastructure as code](../../../02-tools/infrastructure-as-code/), [policy/governance](../../../02-tools/policy-governance/), and [observability](../../../02-tools/observability/) by capability. Some destinations are still under development.

## Compare deployment approaches

A push-oriented design gives a delivery actor authority to change the target. A reconciliation-oriented design gives a target-side component responsibility for converging toward declared state. These descriptions are architectural models, not a claim about a particular product's security.

Compare credential placement, network access, source of truth, drift handling, emergency changes, event recording, and recovery. A reconciliation mechanism still needs a trustworthy desired-state path, compatible application behavior, and meaningful verification. A direct deployment workflow still needs a controlled and reviewable authority model.

Choose a model based on constraints. Do not assume the label “GitOps” proves security or that a green controller status establishes user-visible success.

## Evaluate shared and dedicated execution

Shared execution can reduce duplicated infrastructure and standardize maintenance. It can also connect teams through resource contention, update risk, credentials, or insufficient isolation. Dedicated execution may reduce some boundaries of impact while adding cost and operating work.

Determine whether different workloads have different trust requirements. Untrusted contribution checks and privileged deployment tasks should be assessed separately. Review the platform's exact worker lifecycle and security behavior before defining an isolation claim.

## Test the difficult requirements

A demonstration should include a normal candidate and a relevant negative case. Ask what happens when a verification fails, evidence is missing, access is denied, an artifact differs, an environment drifts, or a dependency becomes unavailable.

Define expected results before testing. Capture the environment and versions, the action, observations, interpretation, and cleanup. A product trial that only shows a successful deployment does not validate recovery or trust boundaries.

DORA's [test automation guidance](https://dora.dev/capabilities/test-automation/) is useful when examining the quality of verification feedback. Tests need to remain relevant and maintainable; adding a gate does not automatically make a release safer.

## Keep an architecture decision record

Record the problem, constraints, options, sources, trial evidence, selected approach, consequences, operational owner, rejected alternatives, and review triggers. Include implementation limits and unsupported workflows.

**Illustrative example:** a hosted build service reduces worker maintenance, but the target environment requires a restricted network path. The decision must explain how that path is provided and controlled, what operational responsibility remains, and how failures affect delivery. A feature comparison alone does not resolve that requirement.

Use cost figures only with dated assumptions and a defined workload. Avoid implying that free access, a license, or a service tier remains available indefinitely.

## Maintain the toolkit

Document supported versions, integrations, ownership, update procedures, incident routes, and retirement criteria for the chosen implementations. Revisit decisions when requirements or evidence change. Keep the number of supported variations manageable and provide a justified exception path.

Continue with [official documentation](official-documentation.md), [production responsibilities](production-responsibilities.md), or the [curriculum](curriculum.md).

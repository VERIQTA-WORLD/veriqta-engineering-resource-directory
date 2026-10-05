# Find a tool

Find a tool by defining the engineering capability you need. A useful tool decision connects a problem, constraints, evidence, and the responsibilities required to operate the result.

This guide is for learners and working engineers. It provides a selection method rather than current product rankings. Tool pages and related references are being developed, so some destinations are still placeholders.

## Describe the problem before searching

“We need an observability tool” is incomplete. Which behavior must be observed? Who needs the evidence? What decision will it support? Which environments must be covered, and how quickly must a useful signal arrive?

Write a requirement in operational terms. For example: “The team needs to investigate slow requests by relating application observations to dependency behavior.” This is an illustrative requirement, not a claim about a particular product.

Separate required capabilities from preferences. A familiar interface may be desirable, but a mandatory integration or data-location constraint can determine suitability.

## Choose the relevant category

The [tools section](../02-tools/) organizes technology by capability. Useful starting points include [delivery](../02-tools/cicd/), [infrastructure as code](../02-tools/infrastructure-as-code/), [containers](../02-tools/containers/), [Kubernetes](../02-tools/kubernetes/), [networking](../02-tools/networking/), [observability](../02-tools/observability/), [security](../02-tools/security/), [databases](../02-tools/databases/), [storage](../02-tools/storage/), and [platform/developer experience](../02-tools/platform-developer-experience/).

A tool can support more than one category. Check its actual capabilities rather than treating folder placement as its complete definition. Use [domains](browse-by-domain.md) if the capability or terminology is unfamiliar.

## Build a requirement record

| Area | Questions to answer |
| --- | --- |
| Outcome | What must the tool enable, and how will success be demonstrated? |
| Environment | Where will it run, and which systems or versions must it support? |
| Integration | What data, identity, APIs, and workflows must it connect to? |
| Scale | What workload and growth assumptions matter? |
| Security | Which permissions, sensitive data, and trust boundaries are involved? |
| Reliability | What happens if the tool or one of its dependencies fails? |
| Operations | Who installs, upgrades, monitors, restores, and supports it? |
| Cost | Which charges and operating effort must be included? |
| Constraints | Which licensing, access, data-location, or organizational limits apply? |
| Exit | How can data and workflows be moved or recovered if the choice changes? |

These questions are a selection framework. The relevant answer depends on the task; not every small utility requires a large architecture assessment.

## Evaluate a short list

Read official documentation for the exact version and deployment mode. Confirm important features, limits, authentication behavior, integration compatibility, and current licensing or commercial terms. A feature name in a marketing description is not sufficient evidence that it meets your requirement.

Use ecosystem material to understand supporting components. Include dependencies that must be operated separately. When comparing hosted and self-managed options, compare the ownership arrangement as well as the feature set.

Popularity can help you discover candidates, but it does not prove suitability. Likewise, familiarity reduces some learning effort but does not remove technical constraints.

## Run a proportionate trial

Define a controlled trial around the required outcome. State the environment, software versions, test data, workload, permissions, expected result, and cleanup. Use synthetic or sanitized data when evaluating with information that should not be exposed.

Test ordinary behavior and at least one important failure condition where practical. Can the team interpret an error? Restore configuration? Detect a failed dependency? Export relevant data? The exact tests should follow the requirements.

Record measured behavior separately from documentation-backed claims and assumptions. A small trial does not prove every production scale or failure condition.

## Make the tradeoff explicit

**Illustrative example:** one candidate provides the required capability with little setup, while another offers greater control but needs additional components and ongoing operation. The decision depends on the team's constraints and ability to own that complexity. “More configurable” is useful only when the control is needed and can be maintained.

Avoid a comparison table that makes every candidate look identical. Explain which difference matters to the workload and why.

## Record the decision

A short decision record should include the problem, must-have requirements, candidates, sources checked, trial evidence, chosen approach, rejected alternatives, operational owner, limitations, and review triggers.

A review trigger might be a changed workload, unavailable support, an integration change, or a cost constraint. Choose triggers that matter to the specific decision rather than assuming every choice must be replaced on a schedule.

If no candidate meets the requirements, revisit the requirements or consider a different architecture. Do not select a tool merely to complete the comparison.

## Connect the choice back to engineering work

Use [technical domains](../03-technical-domains/) to understand the underlying mechanism, [ecosystems](../05-technology-ecosystems/) to understand integrations, and [production problems](../06-production-problems/) to consider operational failures. An evaluated tool is one part of a system, not a substitute for understanding the system.

Return to [Start Here](README.md), or continue to the [tools section](../02-tools/).

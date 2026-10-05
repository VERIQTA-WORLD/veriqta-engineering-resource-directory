# Contribution guide

A useful contribution improves a reader's ability to understand a subject, find a resource, make a decision, or carry out a justified task. You can contribute by correcting an explanation, reporting missing context, improving navigation, adding a well-supported resource, or supplying reproducible verification evidence.

This guide describes a practical contribution package for the directory. Detailed contributor policies, catalogue conventions, templates, and automated checks are still being developed. Do not assume that a placeholder policy is already adopted or that an empty script performs validation.

## Choose a focused improvement

Begin with a specific reader problem. Examples include a broken destination, an undefined term, an instruction missing its execution context, a resource whose version scope is unclear, or a troubleshooting step that does not explain how to interpret its result.

Use the [repository map](repository-map.md) to identify the correct location. Read the file, its folder README, and related pages before proposing a change. The explanation may already exist elsewhere and need a useful link rather than another copy.

For a large addition, describe the proposed scope and its relationship to existing material before creating many files. Preserve the architecture and existing resource identity unless restructuring is part of the agreed change.

## Prepare a useful report

| Information | Why it matters |
| --- | --- |
| Exact path and section | Lets reviewers locate the issue |
| Reader impact | Explains what is unclear, incorrect, or impossible to do |
| Relevant environment | Establishes platform, version, permissions, and context |
| Observation | Distinguishes the actual result from an assumption |
| Expected behavior | Defines the proposed correction or learning outcome |
| Source or reproduction | Gives the reviewer evidence to assess |
| Proposed change | Keeps the improvement focused |
| Known limits | Identifies what has not been checked |

**Illustrative report:** “This guide does not state whether the command runs on the local workstation or the remote host. That affects the path and permissions. Please identify the execution context and add a checkpoint that confirms the intended file was created.”

This is more actionable than “the guide does not work.” Never share credentials, private keys, confidential logs, account details, or personal information in a public report.

## Write for the reader

Explain purpose and assumptions before details. Use clear terminology, realistic examples, and sources that support important claims. Distinguish an illustrative scenario from an actual incident or test.

A resource submission should explain what it teaches or enables, who it is for, its prerequisites, and why it belongs in the collection. A bare URL leaves readers and reviewers to perform that evaluation themselves.

A practical change should include commands or configuration in context, expected observations, interpretation, relevant failure handling, and cleanup. Do not shorten an instruction by removing essential environment details.

## Provide source and verification evidence

Prefer official documentation and other primary sources for behavior-critical claims. Identify the relevant page or section, version, and checked date. Record conflicting or unavailable evidence rather than hiding it.

State exactly what you verified:

- **Source checked:** the cited material supports the claim in the stated context.
- **Statically checked:** syntax, structure, links, or configuration were inspected or validated without demonstrating full execution.
- **Runtime tested:** the procedure ran in a stated environment with recorded observations.
- **Not tested:** the behavior has not been executed; explain why and what remains to be done.

Different parts of one contribution may have different verification levels. Do not label an entire procedure runtime tested because one command ran.

## Respect attribution and reuse

Write original explanations. Attribute external material appropriately and check reuse terms before copying text, images, or datasets. Linking a resource does not grant permission to reproduce it.

Do not submit leaked or proprietary certification material. Do not invent authorship, quotations, product behavior, review approvals, or test evidence. Do not assume that an empty repository license establishes contribution or reuse terms; those terms require an explicit published decision.

## Package the change for review

Provide the files changed, the problem addressed, the resulting reader experience, source support, checks performed, and unresolved limits. Explain any effect on other pages, catalogues, or indexes.

If you submit through the repository's contribution channel, use the applicable published process when it is available. This guide does not assume a particular issue template, automated workflow, or approval rule is already operational.

Keep unrelated edits separate. A correction to one command should not silently redesign a taxonomy or rename resource identifiers across the collection.

## Review the complete reader path

After editing, check that a reader can reach the page, understand its purpose, meet its prerequisites, interpret its examples, follow related links, and understand the remaining limitations. Check spelling, terminology, file paths, anchors, and asset references.

For a larger folder change, verify that each file contributes something distinct and that the files agree on versions, example names, and recommendations. A complete README does not make the rest of a folder complete.

## Where detailed rules will live

The [root contribution file](../CONTRIBUTING.md), [contributor guides](../16-contributor-guides/), [templates](../14-templates/), and [quality assurance section](../15-quality-assurance/) are the intended locations for adopted procedures. The [resource catalogue](../13-resource-catalog/) and [ID naming policy](../ID-NAMING-CONVENTION.md) will establish metadata and identity conventions.

Until those rules are populated, document proposals as proposals. Do not allocate identifiers or claim validation under an unpublished convention. See [Understand resource IDs](understand-resource-ids.md) for the current boundary.

Return to [Start Here](README.md) or use the [repository map](repository-map.md) to locate your proposed improvement.

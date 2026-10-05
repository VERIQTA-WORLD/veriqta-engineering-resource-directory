# Learning resources

Choose resources according to the architectural question you need to answer. This curated route uses primary material to develop reasoning about delivery systems, release operation, verification, and trust.

It is intended for intermediate and advanced engineers. The linked pages were available as public web reading when checked on 5 October 2026; this is not a claim about download, redistribution, course access, or future pricing. No certification course, paid subscription, or purchase is required for the reading route below.

## Recommended reading sequence

| Resource and publisher | Level and prerequisites | Learning purpose | Practice output | Limitation |
| --- | --- | --- | --- | --- |
| [Continuous delivery](https://dora.dev/capabilities/continuous-delivery/), DORA | Intermediate; basic delivery process | Assess delivery improvement beyond product selection | Current-state map and improvement hypothesis | Does not supply a ready-made implementation |
| [Loosely coupled teams](https://dora.dev/capabilities/loosely-coupled-teams/), DORA | Intermediate/advanced; dependencies and release coordination | Examine boundaries that affect independent work | Comparison of architecture options | Organizational context affects application |
| [Test automation](https://dora.dev/capabilities/test-automation/), DORA | Intermediate; build and test fundamentals | Evaluate useful verification feedback | Candidate evidence and test-gap review | Does not define your workload's complete coverage |
| [Release Engineering](https://sre.google/sre-book/release-engineering/), Google SRE | Intermediate/advanced; build, deployment, operations | Study operational release design | Release ownership and dependency map | Google-specific context needs adaptation |
| [Canarying Releases](https://sre.google/workbook/canarying-releases/), Google SRE | Advanced; telemetry and rollout concepts | Examine release evaluation | Candidate/control observation plan | Example signals and thresholds need contextual review |
| [Provenance](https://slsa.dev/spec/v1.2/provenance), SLSA | Intermediate/advanced; build inputs and outputs | Understand artifact-origin information | Evidence-flow model | Origin evidence is not a complete quality guarantee |
| [Build: Track Basics](https://slsa.dev/spec/v1.2/build-track-basics), SLSA | Advanced; build trust and verification | Read the versioned assurance model | Requirement-to-evidence mapping | Requires full applicable specification for compliance claims |
| [Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use), GitHub | Advanced; workflow actors and permissions | Investigate security in a selected delivery platform | Platform-specific threat review | Applies to GitHub Actions; not every platform |

All entries are web articles, book chapters, or specification pages. Publisher identity, scope, and version notes are detailed in [official documentation](official-documentation.md). This is an editorial reading recommendation, not a claim that a learner has completed or personally implemented every example.

## Read actively

Before opening a resource, write the question you expect it to address. Afterwards, record the idea in your own words, the relevant source section, what it changes about your design, and what you still need to verify.

Separate a transferable principle from a context-specific example. A large organization's release arrangement may reveal a useful responsibility boundary without being an appropriate tool architecture for a small team.

Do not measure progress only by chapters read. A useful result is a decision you can explain and test.

## Use peer review to expose gaps

Ask a reviewer to trace a release without your explanation. Can they identify the artifact, configuration, target, evidence, decision owner, and recovery path? Have them introduce one failure condition and ask what happens next.

If the answer depends on information that is absent from the document, revise it. If the answer depends on untested product behavior, add it to the implementation test plan. Do not resolve a review question by claiming a test that has not run.

## Choose additional courses or books carefully

If you add a course, check its intended audience, prerequisites, outcomes, maintenance, access conditions, and whether it teaches decision making as well as execution. Product training can fill an implementation gap but does not automatically cover architectural tradeoffs, ownership, or recovery.

For a book, identify publisher or author, edition, relevant chapters, and the context of examples. For videos or community material, check authorship and source support. Use supplementary explanations without substituting them for official behavior documentation.

Avoid resources that promise universal production readiness or rely on leaked examination material. Certifications may structure learning, but no certificate substitutes for evidence that you can design, validate, and operate the relevant system.

## Integrate learning into the curriculum

Apply reading to the current [curriculum](curriculum.md) stage rather than waiting until every reference has been read. Revise your maps and decisions as new evidence appears. Use the capstone to integrate the work, then define implementation tests for assumptions the tabletop cannot verify.

Continue with [official documentation](official-documentation.md) or return to the [role overview](README.md).

# DevOps architect curriculum

This curriculum develops the ability to assess, design, validate, and evolve a delivery system. Work through the stages in dependency order, using evidence to decide whether you are ready to move on.

It is intended for engineers with basic delivery experience. The exercises below are architecture and review exercises. They do not contain commands, create cloud resources, or demonstrate runtime behavior. Product-specific implementation labs need a separately defined environment and verification plan.

## Prerequisite assessment

Before beginning, explain a service's request path, source-change workflow, build output, deployment destination, configuration, permissions, logs, and recovery options. Demonstrate that you can distinguish a process failure from a dependency or environment problem in a controlled example.

If you cannot explain these clearly, revisit [operating systems](../../../03-technical-domains/01-operating-systems-compute/), [networking](../../../03-technical-domains/03-networking/), [version control](../../../03-technical-domains/06-version-control/), [testing](../../../03-technical-domains/37-testing/), and [CI/CD](../../../03-technical-domains/08-cicd/). Their folders are navigation destinations; assess their maturity before treating them as complete lessons.

Progress is based on outcomes, not a fixed number of weeks or tools. Keep a portfolio directory for your own diagrams, decisions, evidence, and review notes. Use synthetic or sanitized information.

## Stage 1 Understand delivery as a system

Study the difference between integrating changes, keeping software releasable, deploying it, and exposing functionality to users. Understand how manual queues, unclear responsibilities, large changes, and unreliable tests affect the delivery experience.

Trace one change from request through source review, build, verification, promotion, deployment, and operational confirmation. Record where work waits and where it changes hands. DORA's [continuous-delivery guidance](https://dora.dev/capabilities/continuous-delivery/) provides background; avoid treating a pipeline as the entire process.

**Exercise:** map an illustrative change process or an authorized real process. Identify owners, inputs, outputs, failure paths, and available evidence at each step. For invented timing data, label it synthetic.

**Completion evidence:** a current-state map and three prioritized constraints. Explain why each proposed improvement addresses a specific constraint and what observation would show improvement. Avoid arbitrary organization-wide targets.

## Stage 2 Model application and team boundaries

Study dependencies, interface contracts, data ownership, configuration coupling, and the difference between independently deployable components and tightly coordinated releases. Understand how team coordination can constrain a technically automated process.

Draw the service context before detailed infrastructure. Include users, external dependencies, data stores, delivery actors, and owners. State requirements such as acceptable interruption, data correctness, recovery, access, and workload assumptions.

**Exercise:** compare a single deployment unit with a design that separates one component. Identify which requirement motivates separation, what coordination it removes, and which operational responsibilities it adds.

**Completion evidence:** two credible options and an architecture decision record. Defend the selected option without assuming more components mean better architecture. Use [DORA's team and architecture guidance](https://dora.dev/capabilities/loosely-coupled-teams/) as a discussion reference.

## Stage 3 Design builds, artifacts, and verification

Study build inputs, dependency selection, test feedback, artifact identity, retention, and promotion. Understand the difference between rebuilding from a source revision and deploying the exact artifact that was previously evaluated.

Define what evidence associates source, build, artifact, test results, and deployment. Treat provenance as information about origin and production, not proof that the application is defect-free. Read [SLSA provenance](https://slsa.dev/spec/v1.2/provenance) for the specification's meaning.

**Exercise:** produce a release-evidence model. Include source revision, build identity, artifact digest or equivalent immutable identity, configuration reference, verification results, and deployment target. Explain which fields must be verified and by whom.

**Completion evidence:** an artifact flow and a negative case in which the artifact or evidence does not match expectations. Define rejection, escalation, and retention behavior. Do not claim SLSA compliance without evaluating the chosen version's full applicable requirements.

## Stage 4 Design environments and infrastructure changes

Study environment lifecycle, configuration separation, state ownership, access, quotas, network dependencies, secrets, drift, and recovery. Explain which differences between test and production environments matter to the result being evaluated.

Distinguish infrastructure replacement from recovery of data and service behavior. Identify shared resources that cannot be destroyed simply because an application environment is disposable.

**Exercise:** design development, validation, and production contexts for the same service. Specify who creates and changes each, what information is promoted, which data is synthetic, and how shared dependencies are handled.

**Completion evidence:** a lifecycle table, ownership model, and drift scenario. Show how a suspected deviation is investigated before correction. Include a teardown inventory for disposable environments and explicit exclusions for retained resources.

## Stage 5 Design delivery identities and trust boundaries

Study the permissions of developers, build workers, deployment actors, approvers, artifact stores, and runtime services. Distinguish executing untrusted code from authorizing a production change. Identify where secrets, credentials, or sensitive outputs could cross boundaries.

Use the selected platform's documentation for exact behavior. GitHub's [secure use reference](https://docs.github.com/en/actions/reference/security/secure-use) is one example of provider-specific guidance; its rules must not be assumed identical on another product.

**Exercise:** threat-model the release flow. Describe an untrusted contribution, a compromised build worker, and an unauthorized artifact substitution. For each, identify entry point, privileges, affected assets, prevention, detection, and response.

**Completion evidence:** a trust-boundary diagram and access matrix with justified privileges. Explain how emergency access is authorized, recorded, limited, and subsequently reviewed.

## Stage 6 Plan release exposure and data compatibility

Study promotion, deployment, release exposure, health evaluation, rollback, roll-forward, and database compatibility. Compare a small incremental rollout, a parallel-environment switch, and a controlled maintenance-window release against the same requirements.

A canary is useful only if its observations can distinguish a harmful candidate from ordinary variation. Read [Canarying Releases](https://sre.google/workbook/canarying-releases/) for the evaluation problem; do not copy its example thresholds into an unrelated workload.

**Exercise:** describe an application change that also changes stored data. Define which application versions can coexist, which migration steps are reversible, and what happens if the new version fails after writing data.

**Completion evidence:** a release and recovery plan with stop conditions, observation windows, data compatibility constraints, and decision owners. Identify at least one case where code rollback is insufficient.

## Stage 7 Establish operational evidence and readiness

Study user-visible indicators, dependency behavior, deployment events, alerting, diagnostic access, incident coordination, and recovery validation. Distinguish infrastructure status from the outcome users need.

Define the signals needed to evaluate a rollout and investigate a failure. Include what happens when telemetry is missing or delayed. Do not allow absent evidence to silently become a successful evaluation.

**Exercise:** walk through a slow release candidate, a failed dependency, and a missing telemetry stream. For each, identify evidence, competing explanations, decision authority, and recovery verification.

**Completion evidence:** a readiness checklist and diagnostic decision table. A reviewer should be able to explain why each signal matters and what it cannot prove.

## Stage 8 Plan adoption and sustainable ownership

Study pilot scope, documentation, supported defaults, exception handling, compatibility, support, migration, cost, and deprecation. A shared architecture succeeds only if the teams responsible for it can use and maintain it.

**Exercise:** plan adoption of a reusable delivery pattern by two teams with different requirements. Identify shared capabilities, legitimate variation, unsupported extensions, and the feedback route.

**Completion evidence:** a phased adoption plan with owner, pilot acceptance, support boundaries, recovery path, cost assumptions, and review triggers. Explain why it avoids turning the architect into a permanent approval bottleneck.

## Capstone Architecture review tabletop

### Problem and starting state

An illustrative organization operates a web service and database. Builds are automated, but releases depend on manual artifact selection and undocumented environment changes. Teams want reliable, auditable delivery without unnecessary operational complexity.

Use a text editor or diagram tool on your own device. No privileged access, live systems, or paid cloud resources are required. Use fictional names and synthetic observations. Assume no particular platform until you justify one. This is a tabletop exercise, not an executable system.

### Walkthrough

1. Define the users, delivery outcome, constraints, team responsibilities, and unknowns. State assumptions rather than hiding missing facts.
2. Map the current source, build, artifact, environment, deployment, and service paths. Mark manual choices and trust boundaries.
3. Prioritize the risks using impact and available evidence. Explain which risk the first improvement addresses.
4. Compare at least two viable target designs, including a simpler option. Record selection criteria, operational effort, and limitations.
5. Define artifact identity, verification evidence, promotion, access, deployment, and release evaluation. Trace one candidate from source to users.
6. Design the application/data change sequence and recovery plan. Specify compatibility conditions and actions if recovery assumptions fail.
7. Introduce a substituted artifact, failing candidate, unavailable telemetry, and incompatible data change one at a time. Walk through detection, decision, intervention, and verification.
8. Revise the design where the walkthrough exposes a gap. Record what changed and why.
9. Prepare an implementation and handover plan with test requirements, support owners, remaining risks, and a teardown plan for the future test environment.

### Expected results and evidence

Produce a context diagram, delivery flow, trust-boundary view, access matrix, architecture decision record, release/recovery plan, test plan, adoption plan, and tabletop evidence log. Every design assumption should be either supported or marked pending.

Successful evidence shows an identifiable source-to-artifact-to-deployment relationship, bounded privilege, a meaningful release decision, and explicit recovery behavior. It does not claim those controls ran successfully.

### Common failures and correction

If the artifact identity disappears between build and deployment, revise the handoff and verification design. If rollback ignores data changes, revisit compatibility and recovery. If nobody owns an alert or emergency decision, clarify operational responsibilities. If a missing metric allows automatic promotion, define a deliberate unavailable-evidence policy.

Repeat the affected walkthrough after revising the design. Record unresolved implementation questions instead of inventing a pass.

### Cleanup and assessment

Remove synthetic temporary exports you no longer need and keep the final decision and review evidence. No infrastructure teardown is required because this exercise creates no services. For any later implementation, separately specify resources, deletion order, retained data, and residual-charge checks.

Assess the capstone against requirements coverage, alternatives, trust boundaries, failure handling, evidence, ownership, and usability. A serious unresolved release or recovery gap prevents design acceptance. Runtime readiness remains unverified until implementation tests supply evidence.

Return to the [role overview](README.md) or use [production responsibilities](production-responsibilities.md) to challenge your design.

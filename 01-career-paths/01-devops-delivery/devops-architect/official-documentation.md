# Official documentation

Use these primary references to support delivery architecture decisions. They provide research, engineering guidance, a supply-chain specification, and platform-specific security information. Their authority and scope differ; none defines a universal DevOps architect job description.

Source pages were checked on 5 October 2026. This record does not certify that their examples were executed. Living documentation can change, so revisit it when a decision depends on current behavior.

## Reference catalogue

### DORA Continuous delivery

- **Publisher:** DORA.
- **Type:** research-informed capability guidance; living page.
- **Source:** [Continuous delivery](https://dora.dev/capabilities/continuous-delivery/).
- **Use:** assess the relationship between delivery practices, organizational change, architecture, and automation.
- **Prerequisites:** understanding of a basic software change workflow.
- **Limit:** guidance for improvement, not a vendor implementation or a guaranteed result for an individual team.

Use this page during the current-state assessment. Translate its ideas into questions about your process and evidence rather than adopting unsupported targets.

### DORA Loosely coupled teams

- **Publisher:** DORA.
- **Type:** research-informed organizational and architecture guidance; living page.
- **Source:** [Loosely coupled teams](https://dora.dev/capabilities/loosely-coupled-teams/).
- **Use:** examine testing and deployment independence, coordination, and interface boundaries.
- **Prerequisites:** familiarity with services, dependencies, and release processes.
- **Limit:** does not prescribe one topology or require microservices for every organization.

Use it to challenge whether component and team boundaries support the needed delivery outcomes.

### DORA Test automation

- **Publisher:** DORA.
- **Type:** technical-practice guidance; living page.
- **Source:** [Test automation](https://dora.dev/capabilities/test-automation/).
- **Use:** examine verification feedback and responsibility for maintaining useful tests.
- **Prerequisites:** familiarity with automated testing and builds.
- **Limit:** a practical design still needs workload-specific test coverage and failure interpretation.

Use it when deciding what evidence belongs in a candidate's delivery path.

### Google SRE Release Engineering

- **Publisher:** Google SRE, Site Reliability Engineering book.
- **Type:** engineering book chapter.
- **Source:** [Release Engineering](https://sre.google/sre-book/release-engineering/).
- **Use:** study release-system design and collaboration between release and reliability responsibilities.
- **Prerequisites:** basic knowledge of builds, deployments, and service operation.
- **Limit:** examples come from Google's context; their tools and scale are not requirements for your system.

Focus on the reasoning and adapt it to your organization rather than reproducing a large-company arrangement without need.

### Google SRE Canarying Releases

- **Publisher:** Google SRE, The Site Reliability Workbook.
- **Type:** engineering book chapter with examples.
- **Source:** [Canarying Releases](https://sre.google/workbook/canarying-releases/).
- **Use:** examine staged exposure and the evidence needed to evaluate a candidate.
- **Prerequisites:** understanding of request traffic, measurement, and release candidates.
- **Limit:** sample workloads, platform details, and thresholds are not universal defaults.

Use it while designing release evaluation and tests for harmful candidates or misleading signals.

### SLSA Provenance and Build track

- **Publisher:** SLSA collaboration, published through the Linux Foundation.
- **Type:** approved specification pages, explicitly versioned at 1.2.
- **Sources:** [Provenance](https://slsa.dev/spec/v1.2/provenance) and [Build: Track Basics](https://slsa.dev/spec/v1.2/build-track-basics).
- **Use:** understand artifact origin evidence and the build track's assurance model.
- **Prerequisites:** familiarity with build inputs, outputs, identities, and verification.
- **Limit:** this folder does not perform a compliance assessment. Read full applicable requirements before claiming a level.

Use the versioned approved material for a decision tied to that specification. Do not silently replace it with a draft or a similarly named release candidate.

### GitHub Actions Secure use reference

- **Publisher:** GitHub Docs.
- **Type:** platform security reference; living documentation.
- **Source:** [Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use).
- **Use:** investigate privileged execution, untrusted content, workflow dependencies, and token-related security considerations on GitHub Actions.
- **Prerequisites:** familiarity with workflows, event triggers, workers, and permissions.
- **Limit:** platform-specific guidance; it does not establish behavior for other systems or verify your configuration.

Check the exact relevant section again before implementing a security-sensitive workflow.

## Add implementation documentation deliberately

The role does not require one cloud, runtime, or pipeline product. Once a design selects an implementation, add its exact official references for versions, authentication, configuration, compatibility, limits, upgrade behavior, recovery, and commercial terms where relevant.

Record source title, exact URL, relevant section, version, checked date, and the claim it supports. A homepage may identify a publisher but is insufficient support for a detailed behavior claim.

## Resolve disagreements and missing evidence

Compare version, deployment mode, and context before treating two statements as contradictory. Prefer applicable primary evidence. Record unresolved questions and do not turn an assumption into a verified fact.

Source checking and execution checking are separate. Keep runtime observations with their environment and distinguish them from documentation-backed expectations.

Use [learning resources](learning-resources.md) for a reading route, or return to the [overview](README.md).

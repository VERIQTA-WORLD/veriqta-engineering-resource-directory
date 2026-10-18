# DevOps Engineer: Labs and Portfolio Projects

Use these projects to produce evidence relevant to implementing and operating the path from source changes to usable services. Each brief defines what you will build or design, the references you will use, and the evidence you should retain.

## Before you start

Choose one project and read its full source prerequisites, permissions, access requirements, and cleanup instructions. Record versions and dedicated resource names. Use synthetic data and owned lab resources. A design-only project is valid when deployment is impractical; retain assumptions and validation plans instead of invented runtime results.

## Project 1: Build and trace a containerized service

**Problem:** Start with the Docker learning application, then document the path from source revision to an identifiable build result.

**Deliverable:** Retain application instructions, configuration sources, artifact identity, a meaningful functional check, and source attribution.

**Prerequisites and access:** Follow the selected upstream prerequisites. Docker software, Git, and registry or repository accounts may be required.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Change a configuration input in the dedicated lab. Compare startup success with application usability and explain the observed boundary.

**Cleanup:** Use the source cleanup instructions for containers and volumes. Remove public registry artifacts and disposable credentials separately where applicable.

**Scope limit:** Use the upstream tutorial for setup, then verify each extension against your application and environment.

### Implementation resources

### [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/)

**Use it to answer:** How do the application image, runtime configuration, network exposure, and persistent data relate?

- **Start with:** Before you start, then the application workflow.
- **Prerequisites:** Docker software, Git, and the account requirements in the guide.
- **Access and limits:** See the [maintained source annotation](../README.md#source-docker) for publisher context, access conditions, and the key limitation.

### [Pro Git, second edition](https://git-scm.com/book/en/v2)

**Use it to answer:** Which source changes and references explain the artifact or configuration being reviewed?

- **Start with:** Git Basics, then branching and the internals relevant to your question.
- **Prerequisites:** Basic command-line familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-git) for publisher context, access conditions, and the key limitation.

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

## Project 2: Investigate a deployed application

**Problem:** Use a disposable local cluster and a synthetic application whose request path you can inspect.

**Deliverable:** Record client-to-service behavior, workload configuration, relevant observations, hypotheses, and the reasoning that identifies a bounded failure.

**Prerequisites and access:** Use version-compatible tools, a supported runtime, and adequate local capacity. Instrumentation is optional and needs its own setup.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Introduce one known configuration mismatch, then verify both the platform view and a functional request after recovery.

**Cleanup:** Remove the dedicated workload and cluster using the upstream lifecycle instructions. Remove optional telemetry storage created for the exercise.

**Scope limit:** One controlled failure does not establish competence with every networking or cluster fault.

### Implementation resources

### [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/)

**Use it to answer:** Which local cluster setup can reproduce the behavior of interest, and which production assumptions remain absent?

- **Start with:** Installation, creating a cluster, interacting with it, and deletion.
- **Prerequisites:** A supported container runtime, local capacity, and compatible tools.
- **Access and limits:** See the [maintained source annotation](../README.md#source-kind) for publisher context, access conditions, and the key limitation.

### [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)

**Use it to answer:** Which observable boundary separates the current symptom from the competing failure explanations?

- **Start with:** The guide matching the failing application boundary.
- **Prerequisites:** Workload, Service, and namespace familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-debug) for publisher context, access conditions, and the key limitation.

### [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/)

**Use it to answer:** Which signals can connect the user symptom to the dependency or operation you need to inspect?

- **Start with:** Signals relevant to your diagnostic question.
- **Prerequisites:** Basic distributed application and observability concepts.
- **Access and limits:** See the [maintained source annotation](../README.md#source-otel) for publisher context, access conditions, and the key limitation.

## Project 3: Write and rehearse a release decision

**Problem:** Create a release review for a synthetic service with a meaningful user journey and a potentially incompatible dependency.

**Deliverable:** Produce acceptance signals, exposure limits, stop conditions, a recovery decision table, and a communication note.

**Prerequisites and access:** You can perform the decision exercise without deployment. An optional implementation requires an authorized lab and synthetic data.

### Build and investigate

1. State the acceptance condition and record the starting state.
2. Follow the applicable upstream instructions below for the component setup.
3. Complete the project extension and preserve observations separately from interpretation.
4. Investigate the bounded scenario below and verify recovery where implemented.
5. Complete cleanup and record resources intentionally retained.

**Failure or review scenario:** Assume low traffic hides a failing path. Explain what evidence is missing and whether to continue, pause, or add an appropriate test.

**Cleanup:** Remove any optional deployment and retain sanitized observations. Label simulated outcomes separately from executed checks.

**Scope limit:** A design-only canary exercise cannot provide measured confidence or real traffic outcomes.

### Implementation resources

### [Canarying Releases](https://sre.google/workbook/canarying-releases/)

**Use it to answer:** Does the release comparison have enough relevant exposure and signal to support continuing?

- **Start with:** Canary design, comparison signals, and decision criteria.
- **Prerequisites:** Deployment and service-observability familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-canary) for publisher context, access conditions, and the key limitation.

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

**Use it to answer:** Which user behavior should be measured, what target matters, and how will the result inform a decision?

- **Start with:** Selecting indicators, targets, and the improvement process.
- **Prerequisites:** Understanding of user-visible service behavior.
- **Access and limits:** See the [maintained source annotation](../README.md#source-slo) for publisher context, access conditions, and the key limitation.

### [Incident Response](https://sre.google/workbook/incident-response/)

**Use it to answer:** Who coordinates response, preserves the timeline, and verifies that the affected service has recovered?

- **Start with:** Coordination, roles, communication, and follow-up.
- **Prerequisites:** Understanding of service ownership and operational impact.
- **Access and limits:** See the [maintained source annotation](../README.md#source-incident) for publisher context, access conditions, and the key limitation.

## Portfolio evidence and acceptance

| Item | What to include |
| --- | --- |
| Goal | The engineering problem and the user or operator it affects |
| Architecture | Components, dependencies, trust boundaries, and ownership |
| Reproduction | Source instructions, your additions, versions, and access needs |
| Observation | Expected and actual results with relevant context |
| Failure | The bounded fault or design challenge and your reasoning |
| Verification | Evidence that the stated outcome was achieved, or a clear untested status |
| Cleanup | Removed resources, retained resources, credentials, and outstanding costs |
| Attribution | Which implementation material came from external sources |

A passing demonstration supports the stated exercise outcome. Broader security, performance, resilience, and production-readiness claims need their own defined criteria and evidence. If a second person cannot reproduce the result, identify missing prerequisites before expanding scope.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

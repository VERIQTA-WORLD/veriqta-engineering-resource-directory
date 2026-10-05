# Production responsibilities

A DevOps architect helps teams make delivery decisions that remain workable under change and failure. Production responsibility includes validating assumptions, coordinating ownership, and ensuring that the delivery system itself can be operated and recovered.

This guide is for experienced engineers and reviewers. It describes responsibilities and review questions, not a system-specific incident runbook. The organization must assign actual authority, operational ownership, and escalation.

## Establish requirements and a baseline

Begin with the service outcome and constraints. Identify which users depend on the service, the effects of interruption or incorrect data, required access boundaries, workload assumptions, and the team's operating capacity.

Map the current change process. Capture where work waits, where failures occur, and which steps depend on undocumented knowledge. Measure what is relevant to the problem before proposing targets. A faster pipeline is not necessarily an improvement if it promotes incorrect artifacts or makes recovery harder.

The architect should help define the improvement hypothesis, evidence, and decision owner. Product and service owners establish acceptable outcomes; specialists validate relevant technical or organizational constraints.

## Trace the release through the system

A production design should explain how an approved source change becomes a build, an identifiable artifact, a candidate evaluated in context, and a deployment. Include runtime configuration and data changes in that account.

Choose how evidence is retained and verified. A release record should make it possible to identify what ran, where it ran, which configuration it used, and what verification supported the decision. Consider emergency and alternate deployment routes as well as the normal path.

[SLSA's provenance guidance](https://slsa.dev/spec/v1.2/provenance) describes origin information for artifacts. Whether that information is trusted depends on its production and verification model; a file labeled provenance is not sufficient assurance by itself.

## Design access around responsibilities

Identify human and machine actors separately. A build actor may need to fetch dependencies and publish outputs without needing production deployment authority. An application runtime may need access to service data without needing the ability to edit pipelines.

Review how untrusted contributions, scripts, actions, dependencies, and artifacts are processed. Determine which execution contexts can reach sensitive credentials or networks. Use product-specific guidance for the selected platform rather than assuming all runners and triggers behave alike.

The [GitHub Actions secure use reference](https://docs.github.com/en/actions/reference/security/secure-use) discusses risks involving untrusted input and privileged workflows. Use it when assessing GitHub Actions; other platforms need their own documentation.

## Make environment ownership explicit

Define who owns infrastructure state, configuration, networking, secrets, data, and shared services. Clarify which resources are disposable and which need retention, backup, or coordinated changes.

Ask how changes are reviewed, how drift is detected and investigated, and how access is removed. A declaration of intended state does not prove the running system matches it. Avoid correcting every difference automatically when the difference may represent an emergency intervention that still needs assessment.

## Treat deployment and data changes together

Plan the sequence in which schema, data, application behavior, and configuration change. Identify compatible combinations of versions and the point at which a migration becomes difficult or impossible to reverse.

**Illustrative scenario:** a release changes how records are stored. The previous application can no longer interpret newly written records. Reverting the application image may leave the service unable to process those records. The recovery plan must account for data compatibility, not only artifact retention.

Review staged compatibility approaches, migration checkpoints, backups, restore implications, and roll-forward options with the application and database owners. A backup's existence does not prove the service can meet its recovery needs; restore evidence and validation matter.

## Define meaningful rollout evaluation

Select the rollout pattern against workload, risk, observability, and capacity constraints. Determine what candidate population is representative and which measurements distinguish release harm from unrelated variation.

Google's [canarying guidance](https://sre.google/workbook/canarying-releases/) explains the need to evaluate a candidate and connect that evaluation to the release process. A traffic split alone does not establish a sound decision.

Document who can pause exposure, which observations stop promotion, and how the system behaves if evidence is absent. Include low-traffic cases and changes whose effects appear later than the rollout window.

## Design for failure of delivery infrastructure

The pipeline, artifact store, identity service, deployment controller, and telemetry path are dependencies. Their failures can prevent urgent releases or recovery even when the application is still operating.

Separate continuity of the running service from the ability to deliver changes. Identify recovery priorities, retained artifacts, configuration backups, access dependencies, and support ownership. An emergency path must have bounded authority and a reviewable record rather than becoming an undocumented permanent bypass.

## Review production readiness

| Area | Review question | Evidence to request |
| --- | --- | --- |
| Artifact identity | Can the deployment be traced to the intended candidate? | Release record and mismatch rejection test |
| Access | Can an actor exceed its required responsibility? | Permission review and relevant negative tests |
| Configuration | Are required values and secrets supplied through controlled routes? | Configuration inventory and validation evidence |
| Compatibility | Can supported versions coexist during the change? | Contract and migration test results |
| Release evaluation | Can a harmful candidate be distinguished from expected variation? | Signal design and controlled failure evaluation |
| Recovery | Can user-visible service be restored under stated conditions? | Recovery exercise with data checks |
| Delivery dependencies | Can the release system itself be restored? | Dependency map, backups, and recovery evidence |
| Ownership | Does every critical component have support and escalation? | Named responsibilities and handover review |
| Cost and capacity | Are operating and failure-mode requirements affordable? | Dated assumptions and workload evidence |

This table defines review expectations. It does not report that the tests have been performed for a particular system.

## Work during an incident

Support the incident lead and responsible teams with knowledge of delivery history, component boundaries, and recovery options. Preserve evidence, state uncertainty, and avoid making concurrent changes outside the response plan.

Distinguish immediate mitigation from confirmed cause. A failure following a release makes the release relevant but does not by itself prove causation. Compare actual service behavior, deployment evidence, dependencies, and recent changes before recommending a durable correction.

After recovery, examine whether the design made detection, diagnosis, or intervention unnecessarily difficult. Convert lessons into specific controls, tests, or clearer ownership, with acceptance criteria.

## Handover and continuing improvement

Handover includes supported workflows, known limitations, decision records, implementation evidence, operational documentation, support routes, and migration or deprecation rules. The receiving teams should be able to explain the design and demonstrate relevant actions without depending on the architect's memory.

Review shared patterns through controlled adoption. Changes to templates, credentials, runners, and controllers can affect many teams. Pilot them, assess compatibility, and provide a recovery path before broad rollout.

Continue with the [toolkit](toolkit.md), assess the [curriculum capstone](curriculum.md), or return to the [overview](README.md).

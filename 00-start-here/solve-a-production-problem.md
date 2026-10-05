# Solve a production problem

Use this guide to organize an investigation and find the relevant material in the directory. A production symptom is a starting observation, not a diagnosis. The aim is to reduce uncertainty, choose proportionate action, and verify that the affected service has recovered.

This orientation is intended for engineers with responsibility for a system or learners working in an isolated exercise. It is not a system-specific runbook. During a real incident, use your team's response procedures, ownership information, and change controls.

## Establish impact and scope

Describe what users or dependent systems cannot do, when the problem began, and which parts of the service are affected. Distinguish a user report from an observed measurement and a confirmed system condition.

| Question | Useful evidence |
| --- | --- |
| What action is affected? | A failing request or workflow with a time and outcome |
| How broad is the impact? | Comparison across users, locations, service instances, or environments |
| When did it start? | Aligned observations and a timeline of relevant changes |
| Is it continuing or intermittent? | Repeated observations over a defined window |
| What changed? | Releases, configuration, infrastructure, access, traffic, and dependency changes |
| Who owns the affected components? | Service ownership and escalation information |

Align timestamps and account for time zones. Preserve relevant evidence before interventions that could remove it. Coordinate responsibilities so that multiple responders do not make conflicting changes.

The urgency of impact may require mitigation before a complete explanation is available. Record that distinction rather than retroactively calling the mitigation a proven root-cause correction.

## Choose a symptom category

The [production problems section](../06-production-problems/) groups investigations by context:

| Category | Examples of questions to explore |
| --- | --- |
| [Systems](../06-production-problems/systems/) | Is host resource pressure or process behavior involved? |
| [Application and API](../06-production-problems/application-api/) | Which request or dependency is failing? |
| [Networking](../06-production-problems/networking/) | Where does connectivity or traffic behavior differ from expectation? |
| [Containers](../06-production-problems/containers/) | What happens during process startup or container operation? |
| [Kubernetes](../06-production-problems/kubernetes/) | Which workload, controller, service, or cluster boundary needs investigation? |
| [CI/CD](../06-production-problems/cicd/) | Which build, verification, delivery, or release step failed? |
| [Infrastructure as code](../06-production-problems/infrastructure-as-code/) | Do intended state, recorded state, and actual resources differ? |
| [Cloud](../06-production-problems/cloud/) | Which provider-specific service or access boundary is relevant? |
| [Databases](../06-production-problems/databases/) | Is connection, query, resource, or data behavior involved? |
| [Messaging](../06-production-problems/messaging/) | Where does message processing or delivery diverge from expectation? |
| [Storage and backup](../06-production-problems/storage-backup/) | Are access, capacity, persistence, or recovery affected? |
| [Distributed systems](../06-production-problems/distributed-systems/) | Is a partial failure or coordination problem involved? |
| [Edge, DNS, and CDN](../06-production-problems/edge-dns-cdn/) | Where do name resolution or traffic delivery differ? |
| [Observability](../06-production-problems/observability/) | Is the evidence missing, delayed, or misleading? |
| [Platform and developer experience](../06-production-problems/platform-developer-experience/) | Which platform capability or developer workflow is failing? |
| [Security](../06-production-problems/security/) | Are access controls or a possible security event relevant? |
| [AI and GPU](../06-production-problems/ai-gpu/) | Which workload, scheduling, device, or compatibility boundary needs evidence? |

These are browsing routes, not mutually exclusive causes. A failure can cross several boundaries. Destination guides are being developed; do not use an empty or incomplete file as an operational procedure.

## Read a problem folder in the right order

Start with its README and symptoms to confirm the guide's scope. Use triage to establish urgency and first observations. Follow the decision tree for evidence that distinguishes hypotheses. Consult commands and diagnostic tools for execution context and interpretation.

Only then evaluate mitigation against the actual evidence, unless incident urgency already requires a controlled intervention. Use verification to assess recovery, prevention to consider durable changes, and references to check behavior-specific details.

A relevant domain can fill a conceptual gap. Official documentation can resolve a product or version detail. Neither should replace evidence about the running system.

## Keep facts and hypotheses separate

**Illustrative scenario:** requests become slow after a release, and a dashboard reports high CPU use. The timing makes the release relevant, but neither observation proves the release caused the problem or that CPU saturation is the limiting factor.

Ask whether the metric covers the affected instances and time window. Compare workload, request latency, errors, and relevant dependencies. Determine which evidence would distinguish expensive application work, increased demand, a constrained environment, or a dependency-related effect.

These are investigative questions, not a command procedure. The correct checks depend on the environment and permissions. Do not apply every possible diagnostic action at once; choose checks that meaningfully distinguish the current hypotheses.

## Choose actions with explicit consequences

Before acting, establish the target, expected effect, possible disruption, access requirements, rollback or recovery, and verification plan. Prefer an action supported by evidence and proportionate to the impact.

A restart may temporarily restore service while destroying useful process evidence. Scaling may increase capacity without addressing the underlying behavior. A rollback may be unsuitable after an incompatible data change. Evaluate these consequences in the actual system rather than assuming an action is universally safe.

Escalate when access, impact, data integrity, security concerns, or uncertain recovery exceed your authority or understanding. Do not bypass organizational controls to follow a generic guide.

## Verify user-visible recovery

Check the original failing action and relevant dependency behavior. Compare latency, errors, throughput, queues, or resource conditions as appropriate to the incident. Use a meaningful observation window and confirm that one successful request is not masking continuing failures.

Record what changed, what improved, what remains unexplained, and whether temporary measures are still active. Distinguish restored service from completed root-cause analysis.

## Preserve the learning

Capture a timeline, evidence, decisions, interventions, results, and follow-up actions. Assign owners and acceptance criteria for durable corrections. Use [postmortems](../11-postmortems/) to study relevant lessons, while remembering that another incident's cause does not prove this incident's cause.

For lab work, restore the intended state and clean up disposable resources. For production, remove temporary measures through the appropriate change process and verify the result.

Continue to [production problems](../06-production-problems/), use [domains](browse-by-domain.md) for underlying concepts, or return to [Start Here](README.md).

# SRE and Reliability Engineering Resource Directory

Find resources for measuring useful service behavior, understanding failure, controlling change, planning capacity, and recovering dependable operation. Choose the responsibility that matches the question in front of you. You can move between collections as the evidence reveals a different boundary or owner.

## Choose a reliability responsibility

| Collection | What you focus on | Question to investigate |
| --- | --- | --- |
| [Capacity Engineer](capacity-engineer/README.md) | Matching usable resources to current and forecast demand under performance and failure constraints | How much demand can you serve while meeting the latency and recovery requirements, including a lost failure domain? |
| [Chaos Engineer](chaos-engineer/README.md) | Testing explicit resilience hypotheses through bounded, observable fault experiments | Which assumption will the experiment test, what will stop it, and how will you verify recovery? |
| [Cloud Reliability Engineer](cloud-reliability-engineer/README.md) | Making cloud workloads dependable across managed services, identity, quotas, networking, and recovery boundaries | Which cloud dependencies and failure domains determine the workload’s actual recovery capability? |
| [Database Reliability Engineer](database-reliability-engineer/README.md) | Protecting database correctness, availability, performance, and recoverability as connected responsibilities | Can you preserve correct data and useful service behavior through overload, replication failure, and restoration? |
| [Infrastructure Reliability Engineer](infrastructure-reliability-engineer/README.md) | Keeping infrastructure and its change-control dependencies operable, recoverable, and appropriately isolated | Can you repair or rebuild the environment when the infrastructure control path itself is impaired? |
| [Network Reliability Engineer](network-reliability-engineer/README.md) | Maintaining dependable connectivity through naming, routing, transport, policy, and failure-domain analysis | At which boundary does the connection fail, and which observation distinguishes the competing causes? |
| [Platform Reliability Engineer](platform-reliability-engineer/README.md) | Operating shared developer capabilities with explicit tenant boundaries, consumer objectives, and recoverable workflows | Can consumers complete supported tasks when a shared controller, integration, or identity service is degraded? |
| [Reliability Engineer](reliability-engineer/README.md) | Turning user and business requirements into measurable reliability decisions across a system lifecycle | Which failure risk matters most to users, and which intervention has evidence of reducing it? |
| [Resilience Engineer](resilience-engineer/README.md) | Designing and validating continued operation, controlled degradation, and recovery under disruption | What useful service remains during disruption, and can the system recover without unacceptable data loss? |
| [Scalability Engineer](scalability-engineer/README.md) | Understanding how workload growth changes bottlenecks, coordination, resource demand, and service behavior | Which limit constrains useful throughput next, and will the proposed scaling action actually relieve it? |
| [Service Reliability Engineer](service-reliability-engineer/README.md) | Connecting service ownership, user journeys, objectives, dependencies, releases, and recovery | Which user outcome defines service health, and what evidence supports accepting or stopping a change? |
| [Site Reliability Engineer](site-reliability-engineer/README.md) | Applying software engineering to service reliability, operational workload, release safety, and incident learning | Which engineering change will sustainably improve service reliability or reduce recurring operational work? |

## Distinguish closely related questions

| If you need to understand… | Start with… | Then connect it to… |
| --- | --- | --- |
| How much demand the service can sustain | Capacity Engineering | Scalability when the next limit needs architectural change |
| Why adding resources stops helping | Scalability Engineering | Database or platform dependencies that constrain useful work |
| Whether a failure assumption holds | Chaos Engineering | Resilience design and service recovery evidence |
| What remains useful during disruption | Resilience Engineering | Capacity, data integrity, and controlled return to normal |
| Whether users can complete a task | Service Reliability Engineering | The relevant component and dependency observations |
| How to make reliability work sustainable | Site Reliability Engineering | Toil, release decisions, response, and engineering improvements |
| Which reliability risk to prioritize | Reliability Engineering | The specialist responsible for the affected mechanism |

Use the cloud, infrastructure, database, network, and platform collections for their implementation and ownership boundaries. Titles overlap across organizations; the question and required evidence are more useful than a rigid career ladder.

## Choose a resource format

Open a role README for navigation. Use learning resources for a reading sequence, official documentation for exact behavior, architecture resources for alternatives, and production practices for operating decisions. Project pages define practical or design deliverables; assessment pages help you practise applying the reasoning when conditions change.

## Primary references and access notes

Use these descriptions to check prerequisites, access, and technical limits. Select the product version matching your environment and confirm account, software, and service conditions before implementation.

<a id="source-fis"></a>

### [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html)

AWS describes controlled fault experiments against supported resources.

- **Best for:** A dedicated AWS test environment and fault-experiment design.
- **Start with:** Experiment concepts, targets, permissions, and stop conditions.
- **Access:** Free public documentation; experiments, targets, and monitoring may incur charges.
- **Important limit:** Review each action and target selector; cleanup and recovery depend on what the experiment changes.

<a id="source-iam"></a>

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

AWS describes the policy and permission model used to control access.

- **Best for:** AWS identities, resources, and basic JSON familiarity.
- **Start with:** Policy types and the linked evaluation guidance.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Assess all applicable policy layers; one policy document is not the complete effective permission set.

<a id="source-hub"></a>

### [AWS Resilience Hub overview](https://docs.aws.amazon.com/resilience-hub/latest/userguide/what-is.html)

AWS describes application resilience assessment and related recommendations.

- **Best for:** A defined AWS application and its recovery requirements.
- **Start with:** Application scope, policies, assessments, and supported resources.
- **Access:** Free public documentation; check current service pricing and account requirements.
- **Important limit:** An assessment reflects modeled resources and assumptions; it is not an executed restore.

<a id="source-aws-rel"></a>

### [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html)

AWS provides workload reliability design and operating guidance.

- **Best for:** AWS workload components and recovery requirements.
- **Start with:** Foundations, change management, and failure management.
- **Access:** Free public reading; AWS deployment and testing can incur charges.
- **Important limit:** Provider resilience does not establish end-to-end application recovery.

<a id="source-adr"></a>

### [Architecture Decision Records](https://adr.github.io/)

This community-maintained directory collects decision-record guidance and formats.

- **Best for:** A decision with real alternatives and consequences.
- **Start with:** The introductory explanation and a suitable template.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A recorded preference needs evidence and later review; a template cannot supply them.

<a id="source-auth"></a>

### [Backstage authentication](https://backstage.io/docs/auth/)

Backstage documents authentication providers and identity integration.

- **Best for:** Identity-provider and backend configuration familiarity.
- **Start with:** Authentication architecture and your selected provider.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Authentication does not by itself define authorization for catalog or scaffolder actions.

<a id="source-permissions"></a>

### [Backstage permissions overview](https://backstage.io/docs/permissions/overview/)

Backstage introduces permission framework concepts and integration.

- **Best for:** Backend development and authentication familiarity.
- **Start with:** Permission concepts and policy integration.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Each plugin and downstream action needs appropriate enforcement; UI visibility alone is insufficient.

<a id="source-c4"></a>

### [C4 model](https://c4model.com/)

Simon Brown's C4 model provides levels of abstraction for communicating software architecture.

- **Best for:** Knowledge of the system and its dependencies.
- **Start with:** System context, then container diagrams when more detail is needed.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A structural diagram does not establish runtime behavior or recovery correctness.

<a id="source-platforms"></a>

### [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)

CNCF TAG App Delivery discusses platforms, their users, and organizational context.

- **Best for:** Experience with developer workflows and operations.
- **Start with:** Platform capabilities and the platform-as-product discussion.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A capability model must be adapted to local needs and operating capacity.

<a id="source-canary"></a>

### [Canarying Releases](https://sre.google/workbook/canarying-releases/)

Google's workbook examines canary release evaluation.

- **Best for:** Deployment and service-observability familiarity.
- **Start with:** Canary design, comparison signals, and decision criteria.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A small cohort with poor signal coverage can miss important failures.

<a id="source-chaos"></a>

### [Chaos Mesh documentation](https://chaos-mesh.org/docs/)

Chaos Mesh documents fault experimentation for Kubernetes environments.

- **Best for:** Kubernetes administration and a disposable cluster.
- **Start with:** Overview, installation, the chosen fault type, and lifecycle controls.
- **Access:** Free public documentation; local or hosted cluster resources are required.
- **Important limit:** Fault controllers can have substantial authority; target selection and stopping behavior need validation.

<a id="source-finops"></a>

### [FinOps Framework](https://www.finops.org/framework/)

The FinOps Foundation organizes technology-value and cost-management capabilities.

- **Best for:** Access to relevant usage, ownership, and billing context.
- **Start with:** Scope, allocation, ownership, and improvement capabilities.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A resource reduction can harm reliability; evaluate economics with operating requirements.

<a id="source-reuse"></a>

### [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows)

GitHub explains calling and maintaining reusable workflows.

- **Best for:** Working knowledge of a basic workflow.
- **Start with:** Inputs, secrets, permissions, and version references.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Sharing execution logic also creates compatibility and rollout responsibilities.

<a id="source-secure"></a>

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

GitHub describes security considerations for workflow execution and dependencies.

- **Best for:** Understanding of triggers, jobs, and runner access.
- **Start with:** Untrusted input, credentials, and third-party actions.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A secure-use review must include your actual integrations and trust boundaries.

<a id="source-burn"></a>

### [Google SRE Workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/)

Google connects service-level objectives to actionable alerting strategies.

- **Best for:** SLIs, SLO windows, and basic time-series reasoning.
- **Start with:** Error-budget consumption and alerting trade-offs.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Sparse traffic and missing data require explicit treatment; example parameters are not universal defaults.

<a id="source-nasd"></a>

### [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/)

Google demonstrates capacity-aware system design through concrete reasoning.

- **Best for:** Basic throughput, storage, and workload arithmetic.
- **Start with:** Requirements, estimates, component capacity, and failure assumptions.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Numerical examples depend on their assumptions; measure your own workload before making commitments.

<a id="source-postmortem"></a>

### [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/)

Google discusses learning from incidents and turning findings into improvements.

- **Best for:** A service incident timeline and ownership context.
- **Start with:** Incident analysis, action items, and organizational learning.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** An action item needs an owner and evidence of effect; a written report alone does not close the risk.

<a id="source-cascade"></a>

### [Google SRE: Addressing Cascading Failures](https://sre.google/sre-book/addressing-cascading-failures/)

Google examines how resource exhaustion and failure propagation interact.

- **Best for:** Distributed-service operation and capacity familiarity.
- **Start with:** Overload, feedback loops, and recovery discussion.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Examples explain mechanisms; they do not establish which mechanism caused your incident.

<a id="source-toil"></a>

### [Google SRE: Eliminating Toil](https://sre.google/sre-book/eliminating-toil/)

Google explains toil and its relationship to engineering work.

- **Best for:** Familiarity with an operational workflow.
- **Start with:** Characteristics of toil and how to identify repeated operational effort.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Automating a task can introduce maintenance; evaluate total effort and risk rather than counting scripts.

<a id="source-overload"></a>

### [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/)

Google discusses protecting services when demand exceeds available capacity.

- **Best for:** Service metrics, request paths, and workload behavior.
- **Start with:** Load shedding, request handling, and overload controls.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A control must be tested with your request mix and dependencies; admission decisions can affect different users differently.

<a id="source-service"></a>

### [Google SRE: Production Services Best Practices](https://sre.google/sre-book/service-best-practices/)

Google presents practices for dependable production services.

- **Best for:** Application operation and distributed dependencies.
- **Start with:** Request handling, dependencies, and the relevant operating concern.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Local workloads and ownership determine which practices are appropriate.

<a id="source-k6"></a>

### [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/)

Grafana explains test types for investigating application load behavior.

- **Best for:** Basic scripting, an authorized target, and relevant telemetry.
- **Start with:** The test type matching your question, then its workload model.
- **Access:** Free public documentation; execution environment and hosted offerings have separate conditions.
- **Important limit:** A load generator can become the bottleneck; validate the offered workload as well as the target.

<a id="source-slo"></a>

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

Google's workbook discusses service-level objectives and their implementation.

- **Best for:** Understanding of user-visible service behavior.
- **Start with:** Selecting indicators, targets, and the improvement process.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Targets require product and operational judgment; example values are not universal requirements.

<a id="source-incident"></a>

### [Incident Response](https://sre.google/workbook/incident-response/)

Google's workbook discusses organized incident response through examples.

- **Best for:** Understanding of service ownership and operational impact.
- **Start with:** Coordination, roles, communication, and follow-up.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Local escalation and authority arrangements must be explicit.

<a id="source-debug"></a>

### [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)

The Kubernetes project organizes application diagnostic references.

- **Best for:** Workload, Service, and namespace familiarity.
- **Start with:** The guide matching the failing application boundary.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A symptom requires local evidence; a diagnostic catalog does not establish its cause.

<a id="source-kube-dns"></a>

### [Kubernetes: Debugging DNS Resolution](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/)

Kubernetes provides a DNS investigation guide for cluster workloads.

- **Best for:** Pod DNS behavior, cluster access, and network basics.
- **Start with:** Prerequisites and the checks matching the failing boundary.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Use your cluster context deliberately; DNS answers alone do not establish application reachability.

<a id="source-disruption"></a>

### [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/)

Kubernetes describes workload disruptions and disruption-budget concepts.

- **Best for:** Replicas, controllers, and service availability.
- **Start with:** Voluntary and involuntary disruption and budget limits.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A disruption budget does not prevent every kind of failure or guarantee spare capacity.

<a id="source-hpa"></a>

### [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/)

Kubernetes describes automatic adjustment of workload replica counts.

- **Best for:** Workload controllers, metrics availability, and resource configuration.
- **Start with:** Metrics, control behavior, readiness, and stabilization.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Replica changes require downstream capacity and time to become useful; limits and dependencies still matter.

<a id="source-resources"></a>

### [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/)

Kubernetes explains workload resource requests, limits, and enforcement considerations.

- **Best for:** Pods, nodes, scheduling, and application resource behavior.
- **Start with:** The resource type and scheduling/runtime behavior relevant to the workload.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** CPU and memory controls have different effects; a scheduling request is not a complete capacity model.

<a id="source-kernel-net"></a>

### [Linux kernel networking documentation](https://docs.kernel.org/networking/index.html)

Linux maintainers provide networking subsystem documentation.

- **Best for:** Linux networking and familiarity with kernel versions.
- **Start with:** The subsystem relevant to your observed host-network behavior.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** This is a specialist reference directory; select the topic and version rather than treating it as a beginner course.

<a id="source-otel"></a>

### [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/)

OpenTelemetry explains the telemetry signals used to describe system behavior.

- **Best for:** Basic distributed application and observability concepts.
- **Start with:** Signals relevant to your diagnostic question.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Instrumentation does not automatically supply storage, retention, or an actionable alert.

<a id="source-pg-conn"></a>

### [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html)

PostgreSQL documents connection-related server configuration.

- **Best for:** Database administration and application connection behavior.
- **Start with:** Connection settings and their resource implications.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** More permitted connections do not necessarily provide more useful throughput; inspect memory and workload effects.

<a id="source-pg-pitr"></a>

### [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html)

PostgreSQL explains WAL archiving and recovery from a base backup.

- **Best for:** Backup administration, WAL concepts, and a version-matched environment.
- **Start with:** Base backup prerequisites, archiving, and recovery configuration.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Restore into a separate target; archived WAL availability and continuity affect recoverability.

<a id="source-pg-stats"></a>

### [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html)

PostgreSQL documents statistics used to observe database activity.

- **Best for:** SQL access and knowledge of the installed PostgreSQL release.
- **Start with:** The relevant activity, replication, I/O, or database statistics views.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Visibility depends on permissions and view semantics; counters and sampled observations need context.

<a id="source-pg-ha"></a>

### [PostgreSQL: High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/high-availability.html)

PostgreSQL documents replication and availability approaches.

- **Best for:** SQL, PostgreSQL administration, and primary/standby concepts.
- **Start with:** The comparison of approaches, then the applicable replication section.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Replication choices affect consistency and failure behavior; replication is not a substitute for backups.

<a id="source-rules"></a>

### [Prometheus: Unit testing rules](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/)

Prometheus documents tests for recording and alerting rules.

- **Best for:** PromQL, rule evaluation, and compatible promtool.
- **Start with:** Test file format, input series, and expected rule results.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Synthetic series tests do not establish that instrumentation, scraping, or notification delivery works end to end.

<a id="source-python"></a>

### [Python subprocess reference](https://docs.python.org/3/library/subprocess.html)

The Python standard-library reference describes process execution and result handling.

- **Best for:** Basic Python and process/exit-status knowledge.
- **Start with:** Frequently used arguments and security considerations.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Shell interpretation and process side effects need deliberate control; select your Python version.

<a id="source-dns"></a>

### [RFC 1035: Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035)

The RFC describes foundational DNS messages and implementation concepts.

- **Best for:** DNS terminology and packet-level reading familiarity.
- **Start with:** Message structure, resource records, and caching concepts.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Read the RFC status and updates; modern DNS behavior also depends on later specifications and resolver implementation.

<a id="source-tls"></a>

### [RFC 8446: TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446)

The RFC specifies TLS 1.3 protocol behavior.

- **Best for:** Transport networking and cryptographic protocol familiarity.
- **Start with:** Handshake concepts and the part relevant to your connection problem.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Certificate operations and older protocol implementations need their own matching references.

<a id="source-state"></a>

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

HashiCorp explains how Terraform tracks managed infrastructure through state.

- **Best for:** Basic Terraform configuration and provider knowledge.
- **Start with:** The purpose of state and its relationship to resources.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** State may contain sensitive values; its storage and access need explicit controls.

<a id="source-locking"></a>

### [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking)

HashiCorp describes state locking and its dependence on backend support.

- **Best for:** Understanding of the selected backend and active operations.
- **Start with:** Lock behavior and force-unlock conditions.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A lock error alone does not establish that no operation is still running.

<a id="source-kind"></a>

### [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/)

The kind project documents local Kubernetes cluster creation and deletion.

- **Best for:** A supported container runtime, local capacity, and compatible tools.
- **Start with:** Installation, creating a cluster, interacting with it, and deletion.
- **Access:** Free public guide; local software and machine resources are required.
- **Important limit:** Local clusters do not model every cloud load balancer, storage system, or failure domain.

## Use the resources together

Begin with a user outcome and a concrete question. Read enough to explain the mechanism, then choose the appropriate reference or bounded exercise. Keep observations separate from assumptions and connect the result to an owned decision. A successful deployment, healthy component, completed fault action, or finished backup each establishes a narrower fact than dependable end-to-end service.

When another responsibility owns the next boundary, share the relevant observations, timing, scope, and question. Use the neighboring collections to build a coherent investigation or design rather than collecting unrelated tools.

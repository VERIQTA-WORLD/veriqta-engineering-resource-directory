# DevOps architect: production-practice resources

[DevOps architect resource directory](README.md)

Use these resources when your architecture needs operating evidence: safe changes, meaningful alerts, identity controls, fault containment, diagnosis, restore procedures, and incident learning. The links provide guidance and references; they do not authorize changes to a live environment.

Service-level indicators (SLIs) measure user-facing behavior. Service-level objectives (SLOs) set the target you operate against. Recovery time objectives (RTOs) and recovery point objectives (RPOs) describe restoration time and acceptable data loss.

## Find resources by topic

- [Release acceptance canaries and rollback](#release-acceptance-canaries-and-rollback)
- [Objectives telemetry and actionable alerts](#objectives-telemetry-and-actionable-alerts)
- [Timeouts retries overload and failure containment](#timeouts-retries-overload-and-failure-containment)
- [Incident coordination and diagnostic references](#incident-coordination-and-diagnostic-references)
- [Backup restoration and disaster-recovery evidence](#backup-restoration-and-disaster-recovery-evidence)
- [Deployment identity supply-chain policy and audit](#deployment-identity-supply-chain-policy-and-audit)
- [Learn from original incident reports](#learn-from-original-incident-reports)
- [Operating-model and cost reviews](#operating-model-and-cost-reviews)

## Release acceptance canaries and rollback

Evaluate the candidate artifact, deployment scope, observation window, success criteria, and abort conditions. Rollback needs compatibility with data and dependent services; reverting a manifest may not reverse every effect.

- **[Release engineering](https://sre.google/sre-book/release-engineering/)** — Study an original account of build, release, and deployment engineering. Intermediate to advanced; Google-specific practices require adaptation.

- **[Canarying releases](https://sre.google/workbook/canarying-releases/)** — Review candidate evaluation, rollout design, and the limits of release signals. Advanced; comparison quality and observation design determine whether a canary is informative.

- **[Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf)** — Review compatibility and recovery concerns when versions coexist or change. Advanced; official PDF. Application and schema compatibility must be tested in your own system.

- **[Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/)** — Kubernetes rollout control for canary and blue-green strategies, including traffic management and analysis integration. Advanced; traffic routing and metrics integrations determine what a rollout can actually verify.

- **[Flagger](https://docs.flagger.app/)** — Automated progressive delivery for Kubernetes workloads using metrics and supported traffic integrations. Advanced; verify supported providers and analysis behavior for the chosen environment.

- **[Pete Hodgson: Feature Toggles, published on MartinFowler.com](https://martinfowler.com/articles/feature-toggles.html)** — Discusses toggle categories, configuration, rollout, and the complexity introduced by long-lived flags. Public engineering article; feature flags separate some release decisions from deployment but introduce testing and retirement work.

- **[GitHub Actions: Deployment environments](https://docs.github.com/en/actions/how-tos/deploy/configure-and-manage-deployments/manage-environments)** — Describes environment protection, deployment configuration, and environment secrets. Public official guide; feature availability depends on repository visibility and plan. Evaluate emergency access and approval ownership.

## Objectives telemetry and actionable alerts

Tie alerts to useful decisions and user outcomes. Metrics, traces, and logs help explain a failure, but their collection and storage pipelines also need capacity, access, and operating ownership.

- **[Implementing SLOs](https://sre.google/workbook/implementing-slos/)** — Review practical service-level objective design and adoption. Intermediate; useful measures depend on service behavior and user expectations.

- **[Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/)** — Compare alerting approaches based on reliability objectives and budget consumption. Advanced; validate alert behavior against real traffic and responder capacity.

- **[OpenTelemetry Collector](https://opentelemetry.io/docs/collector/)** — Review telemetry reception, processing, export, and deployment concerns. Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling.

- **[Prometheus](https://prometheus.io/docs/introduction/overview/)** — Metrics collection and querying with a time-series data model, PromQL, and alerting integrations. Intermediate; plan label cardinality, retention, storage, and availability.

- **[Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/)** — Alert routing, grouping, inhibition, and silencing for alerts from compatible sources. Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery.

- **[Grafana Loki](https://grafana.com/docs/loki/latest/)** — A log aggregation system with label-based indexing and query integration; evaluate retention, cardinality, and tenant access. Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance.

- **[Jaeger](https://www.jaegertracing.io/docs/)** — Distributed tracing software for following requests across services and investigating latency or errors. Intermediate; instrumentation coverage and sampling affect what can be observed.

## Timeouts retries overload and failure containment

Account for dependencies, deadlines, retry budgets, idempotency, and failure domains. Multiple individually reasonable retry policies can amplify a shared failure.

- **[Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf)** — Review dependency-call behavior and retry amplification risks. Advanced; official PDF. Values require latency and failure evidence from your own system.

- **[Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/)** — Study duplicate-request handling and API design trade-offs. Advanced; operation semantics determine which retry behavior is safe.

- **[Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/)** — Review overload, feedback loops, and failure propagation. Advanced; validate containment strategies with bounded tests and measurements.

- **[Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/)** — Compare patterns addressing distributed-system concerns and trade-offs. Intermediate; examples are provider-oriented, while many problem statements apply more broadly.

- **[Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/)** — Review requests, limits, scheduling, and resource constraints. Intermediate; workload measurements and node capacity are needed for useful settings.

- **[Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)** — Review health-check semantics and configuration. Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies.

- **[Kubernetes disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/)** — Understand availability during voluntary and involuntary disruptions. Intermediate; a disruption budget is not a universal guarantee against outages.

## Incident coordination and diagnostic references

Establish command, communication, evidence, and recovery ownership during an incident. Use component references to interpret observations; a symptom is not sufficient evidence for a destructive change.

- **[Managing incidents](https://sre.google/sre-book/managing-incidents/)** — Review incident roles, coordination, communication, and operational response. Intermediate; adapt role separation to team size and actual on-call arrangements.

- **[Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)** — Locate workload debugging references for deployment and runtime failures. Intermediate; establish scope before applying changes. Read permissions and command effects.

- **[Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/)** — Inspect capture and protocol-analysis workflows for network diagnosis. Intermediate; use packet captures only where authorized. Captures can expose credentials and personal or customer data; the retrieved guide identifies a development build.

- **[The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)** — Study implementation-oriented reliability practices and case studies. Intermediate to advanced; openly readable. Requires familiarity with service operation.

- **[Microsoft Engineering Playbook](https://microsoft.github.io/code-with-engineering-playbook/)** — Publishes engineering practices for design, testing, delivery, code review, and team collaboration. Public organizational playbook; adapt its practices to your context rather than treating one organization's process as universal.

## Backup restoration and disaster-recovery evidence

Choose restoration evidence for both configuration and application data. Verify dependency order, permissions, replacement capacity, data integrity, and the expected recovery window. A backup completion message does not prove recoverability.

- **[Velero documentation](https://velero.io/docs/)** — Use the backup and restore references to define the Kubernetes resources and storage integrations included in a recovery test. Advanced; rehearse restore and verify application data consistency, not only object recreation.

- **[PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html)** — Review database backup approaches and their operational implications. Advanced; use documentation matching the deployed database version and test restored data.

- **[Operating etcd clusters for Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/)** — Explains etcd operation, backups, and control-plane considerations for Kubernetes. Advanced administration reference; managed control planes may hide or delegate these operations.

- **[AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html)** — Compare recovery strategies and resilience considerations for AWS workloads. Advanced; define recovery time and recovery point objectives and test the complete workload.

- **[Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview)** — Locate Azure disaster-recovery concepts and planning guidance. Advanced; service support and workload dependencies determine feasible recovery objectives.

- **[Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide)** — Review recovery planning, objectives, and scenario selection. Advanced; test identity, configuration, data, and traffic restoration together.

## Deployment identity supply-chain policy and audit

Treat build runners and deployment credentials as privileged infrastructure. Restrict the identities that can promote artifacts, change trust policy, or bypass a control, and retain evidence of those actions.

- **[GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions)** — Review runner trust, workflow access, and delivery credential exposure. Intermediate; public contributions and privileged jobs need distinct trust treatment.

- **[GitHub Actions: OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect)** — Explains federated workflow identity for obtaining short-lived credentials from supporting cloud providers. Public official concept guide; trust conditions still need to constrain repository, workflow, environment, and audience.

- **[Jenkins security guidance](https://www.jenkins.io/doc/book/security/)** — Review controller access, authorization, and security configuration. Advanced; plugin and agent boundaries also need review.

- **[SLSA specification](https://slsa.dev/spec/)** — Use the specification to define which provenance and security evidence production promotion must verify. Advanced; consult the relevant stable version and track specification changes.

- **[NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final)** — Review secure development practices and their organizational integration. Intermediate to advanced; use the publication's stated scope and any applicable local requirements.

- **[Kyverno](https://kyverno.io/docs/)** — Review policy behavior and exceptions when an admission control can interrupt a deployment or block recovery work. Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests.

- **[Kubernetes security checklist](https://kubernetes.io/docs/concepts/security/security-checklist/)** — Review controls for cluster and workload operation. Intermediate; assign each control an owner and evidence source.

- **[AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)** — Review identity, permissions, credentials, and access-management guidance. Intermediate; combine with service-specific permissions and organization policies.

## Learn from original incident reports

Read the original timeline and contributing factors before extracting a lesson. These historical reports are useful for design review; they do not describe the organizations' current architecture.

- **[Cloudflare outage report, July 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/)** — Study an original account of a software change, resource exhaustion, and recovery. Advanced; historical incident, not a description of the company's current architecture.

- **[GitLab database outage report, January 2017](https://about.gitlab.com/blog/2017/02/01/gitlab-dot-com-database-incident/)** — Study an original recovery incident and the importance of tested backup procedures. Advanced; historical incident. Distinguish recorded facts from assumptions about present systems.

- **[Postmortem culture](https://sre.google/sre-book/postmortem-culture/)** — Review incident learning, documentation, and follow-up practices. Intermediate; focus on evidenced contributing factors and actionable improvement.

## Operating-model and cost reviews

Include rotation, upgrades, capacity, support, cost allocation, and end-of-life work in the architecture. Cost estimates and allocation tools need reconciliation with actual usage and bills.

- **[AWS Well-Architected: Operational Excellence](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/welcome.html)** — Organizes operating-model, preparation, operations, and improvement guidance for AWS workloads. Public official pillar guide; adapt the questions to your ownership model and pair them with implementation evidence.

- **[AWS Well-Architected: Reliability](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html)** — Covers workload foundations, resilient design, change management, and failure recovery. Public official pillar guide; AWS assumptions and implementation examples do not apply unchanged to every environment.

- **[FinOps Framework](https://www.finops.org/framework/)** — Use the FinOps Foundation framework to connect operating decisions, cost accountability, and improvement work. Intermediate; apply using actual operating and billing evidence.

- **[Infracost](https://www.infracost.io/docs/)** — Cost estimates and changes for supported infrastructure definitions before deployment. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees.

- **[OpenCost](https://opencost.io/docs/)** — Kubernetes cost allocation based on resource usage and pricing inputs. Intermediate; allocation assumptions, data quality, and shared costs need review.

## Turn guidance into a review question

For each production requirement, name the owner, the signal or artifact that demonstrates it, and the response when it fails. Record assumptions that still need an experiment or restore test. This page's source review is not evidence that those tests have run in your environment.

## Continue exploring

[Compare tools](devops-architect-tools-and-technologies.md) · [Find official references](devops-architect-official-documentation.md) · [Explore architecture resources](devops-architect-architecture-resources.md) · [Find practical projects](devops-architect-labs-and-portfolio-projects.md)

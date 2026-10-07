# DevOps architect: architecture resources

[DevOps architect resource directory](README.md)

Use this collection to turn a delivery requirement into a design you can explain and evaluate. Start with the system boundary, ownership, failure assumptions, and quality requirements. The resources cover delivery architecture, cloud foundations, shared platforms, security, telemetry, data recovery, and architectural communication.

Some links are architecture libraries or book descriptions. They are labeled as discovery resources rather than complete reference implementations.

## Find resources by topic

- [Describe decisions boundaries and quality requirements](#describe-decisions-boundaries-and-quality-requirements)
- [Independent delivery and organizational boundaries](#independent-delivery-and-organizational-boundaries)
- [Provider architecture libraries and review frameworks](#provider-architecture-libraries-and-review-frameworks)
- [Landing zones and cloud control boundaries](#landing-zones-and-cloud-control-boundaries)
- [Managed Kubernetes and shared-platform designs](#managed-kubernetes-and-shared-platform-designs)
- [Delivery trust and threat modeling](#delivery-trust-and-threat-modeling)
- [Reliability telemetry and failure containment](#reliability-telemetry-and-failure-containment)
- [Data recovery and infrastructure economics](#data-recovery-and-infrastructure-economics)

## Describe decisions boundaries and quality requirements

Use a system view to show people and dependencies, a decision record to explain a choice, and quality scenarios to make requirements testable. An elaborate diagram cannot compensate for an unstated assumption.

- **[C4 model](https://c4model.com/)** — Choose system-context, container, component, and supporting views that show the boundaries relevant to your architecture discussion. Foundation onward; diagrams communicate structure but do not establish operational correctness.

- **[Architecture Decision Records](https://adr.github.io/)** — Find formats and examples for explaining a design choice, its context, alternatives, and consequences. Foundation onward; keep decisions connected to evidence and later changes.

- **[arc42 architecture documentation template](https://arc42.org/)** — Provides a structure for documenting goals, constraints, building blocks, quality requirements, decisions, and risks. Public template and examples; use the relevant sections instead of filling every heading mechanically.

- **[Structurizr documentation](https://docs.structurizr.com/)** — Architecture-modeling tooling for generating consistent views from a shared system model. Intermediate; distinguish modeling tools and available deployment or service options.

- **[Mermaid](https://mermaid.js.org/intro/)** — Text-based diagram syntax and rendering for flow, sequence, and other supported diagram types. Foundation onward; renderer versions and supported diagram features differ between publishing platforms.

- **[SEI: Architecture Tradeoff Analysis Method](https://www.sei.cmu.edu/library/the-architecture-tradeoff-analysis-method/)** — Introduces a structured method for evaluating architectural choices against quality attributes and stakeholder scenarios. Public SEI paper description and download route for the foundational method; detailed application requires preparation and stakeholder participation.

- **[Fundamentals of Software Architecture](https://www.thoughtworks.com/en-us/insights/books/fundamentals-of-software-architecture)** — Introduces Mark Richards and Neal Ford's book about architecture characteristics, styles, and the architect's work. Public book description and related discussion; the book itself is commercial. Broader software architecture, not a DevOps implementation manual.

- **[Building Evolutionary Architectures](https://evolutionaryarchitecture.com/)** — Provides author-associated book information and supporting material on incremental architectural change and fitness functions. Commercial book with public supporting material; use it to think about keeping design constraints testable as systems change.

## Independent delivery and organizational boundaries

Assess whether a service can be tested, deployed, and recovered independently. Team boundaries, shared infrastructure, shared data, and tightly coupled releases all affect that answer.

- **[DORA: Loosely coupled teams](https://dora.dev/capabilities/loosely-coupled-teams/)** — Connects independent delivery to team boundaries and software architecture. Useful when release coordination is a bottleneck; an organization chart alone cannot establish independent deployability.

- **[DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)** — Explains the practices and organizational conditions behind releasing software safely on demand. Public research-backed capability guide; use it to identify improvement hypotheses, not to choose a pipeline product.

- **[DORA: Deployment automation](https://dora.dev/capabilities/deployment-automation/)** — Describes automated deployment, shared ownership, and removal of fragile manual steps. Use it to assess repeatability and handoffs; implementation details depend on your runtime and deployment model.

- **[CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)** — Use the CNCF white paper to examine what an internal platform provides, who it serves, and how its capabilities become usable. Intermediate; platform design must start with developer and operator needs.

- **[Team Topologies resources](https://teamtopologies.com/)** — Explore the authors' model for team boundaries and interaction modes. Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions.

- **[The Twelve-Factor App](https://12factor.net/)** — Review application configuration, deployment, and operability principles. Foundation to intermediate; useful design guidance, not a complete security or resilience architecture.

- **[Martin Fowler: Continuous Integration](https://martinfowler.com/articles/continuousIntegration.html)** — Explains continuous integration practices, integration frequency, build feedback, and common misunderstandings. Public author article; use it to distinguish CI as a working practice from a server that happens to run builds.

## Provider architecture libraries and review frameworks

These are starting points for locating workload designs and conducting reviews. Select designs by workload, constraints, and failure expectations instead of copying a diagram because it uses familiar services.

- **[AWS Architecture Center](https://aws.amazon.com/architecture/)** — Discover architecture guidance and reference material by workload and concern. Intermediate to advanced; evaluate publication scope and required AWS services.

- **[Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/)** — Compare reference architectures, patterns, and decision guidance. Intermediate to advanced; implementation choices and estimates require workload-specific validation.

- **[Google Cloud Architecture Center](https://cloud.google.com/architecture)** — Find architecture guides and implementation references for Google Cloud. Intermediate to advanced; filter by your workload and operational constraints.

- **[AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)** — Review AWS workload decisions and architectural trade-offs. Intermediate to advanced; provider-specific framework, not an independent compliance audit.

- **[Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/)** — Structure Azure workload reviews around documented quality concerns. Intermediate to advanced; tailor review depth to business and workload needs.

- **[Google Cloud Well-Architected Framework](https://cloud.google.com/architecture/framework)** — Structure Google Cloud workload architecture reviews. Intermediate to advanced; provider-specific assumptions require interpretation.

- **[Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/)** — Compare patterns addressing distributed-system concerns and trade-offs. Intermediate; examples are provider-oriented, while many problem statements apply more broadly.

## Landing zones and cloud control boundaries

Account and subscription structure, identity, network connectivity, audit, and policy need an operating model. Compare how each provider blueprint assigns authority and changes the foundation.

- **[AWS Control Tower documentation](https://docs.aws.amazon.com/controltower/)** — Explore governed multi-account foundations and service operations. Advanced; organizational decisions, identity, networking, and account policies remain essential.

- **[Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)** — Review enterprise-scale platform foundations and design areas. Advanced; tailoring and operating ownership are required before deployment.

- **[Google Cloud enterprise foundations blueprint](https://docs.cloud.google.com/architecture/blueprints/security-foundations)** — Review an opinionated approach to organizational cloud foundations. Advanced; blueprint choices are assumptions to evaluate, not mandatory design decisions.

- **[Google Cloud example foundation](https://github.com/terraform-google-modules/terraform-example-foundation)** — Inspect infrastructure code for enterprise foundation patterns. Advanced; substantial organization, permission, and billing prerequisites. Treat as a reference implementation, not a starter lab.

## Managed Kubernetes and shared-platform designs

Evaluate the control plane, worker placement, tenant boundaries, ingress, secrets, observability, and recovery. A reference implementation is a starting design whose dependencies you must operate.

- **[Amazon EKS best practices](https://docs.aws.amazon.com/eks/latest/best-practices/introduction.html)** — Review Kubernetes workload and cluster-design guidance for EKS. Advanced; EKS-specific assumptions must be separated from general Kubernetes advice.

- **[AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks)** — Examine a documented infrastructure baseline for an Azure Kubernetes Service cluster. Advanced; adapt identity, network, availability, and cost choices to requirements.

- **[AKS baseline implementation](https://github.com/mspnp/aks-baseline)** — Inspect the infrastructure sample accompanying the AKS baseline architecture. Advanced; review the repository's current instructions and required Azure resources before deploying.

- **[Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/)** — Review isolation choices and their limitations. Advanced; namespaces alone do not provide every required isolation boundary.

- **[Production Kubernetes environments](https://kubernetes.io/docs/setup/production-environment/)** — Compare production setup considerations and operating models. Advanced; managed services retain workload and configuration responsibilities.

- **[Backstage](https://backstage.io/docs/overview/what-is-backstage/)** — A developer-portal framework with a software catalog, templates, and plugin integrations. Intermediate; catalog quality and plugin maintenance need ownership. A portal alone is not a complete platform.

- **[Backstage Software Templates](https://backstage.io/docs/features/software-templates/)** — Explains template-based project scaffolding and the actions used to produce software repositories. Public project documentation; review action permissions and input handling rather than equating scaffolding with production readiness.

## Delivery trust and threat modeling

Model the path from a source change to an authorized production artifact. Include identity compromise, untrusted contributions, build isolation, evidence verification, policy exceptions, and emergency delivery.

- **[SLSA specification](https://slsa.dev/spec/)** — Use the specification when defining what evidence and build guarantees an artifact-promotion design must require. Advanced; consult the relevant stable version and track specification changes.

- **[NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final)** — Review secure development practices and their organizational integration. Intermediate to advanced; use the publication's stated scope and any applicable local requirements.

- **[OWASP Threat Modeling](https://owasp.org/www-community/Threat_Modeling)** — Explains threat-modeling activities and questions for identifying design risks and mitigations. Public community guidance; review actual assets, trust boundaries, attack paths, and assumptions for your system.

- **[GitHub Actions: OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect)** — Use the workflow-identity model to reason about a cloud deployment trust boundary without embedding long-lived cloud credentials in the pipeline. Public official concept guide; trust conditions still need to constrain repository, workflow, environment, and audience.

- **[SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/)** — Workload identity specifications and concepts for identifying services across trust domains. Advanced; workload identity complements rather than replaces application authorization.

- **[OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/)** — Structure application-security verification requirements for platform-facing services. Intermediate to advanced; choose a version and applicable verification scope.

## Reliability telemetry and failure containment

Service-level objectives (SLOs) describe the outcome you need; design reviews should connect them to dependency behavior, alerting, release checks, and recovery. Timeouts and retries require a system-wide budget.

- **[Implementing SLOs](https://sre.google/workbook/implementing-slos/)** — Review practical service-level objective design and adoption. Intermediate; useful measures depend on service behavior and user expectations.

- **[Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/)** — Compare alerting approaches based on reliability objectives and budget consumption. Advanced; validate alert behavior against real traffic and responder capacity.

- **[Canarying releases](https://sre.google/workbook/canarying-releases/)** — Review candidate evaluation, rollout design, and the limits of release signals. Advanced; comparison quality and observation design determine whether a canary is informative.

- **[Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf)** — Review compatibility and recovery concerns when versions coexist or change. Advanced; official PDF. Application and schema compatibility must be tested in your own system.

- **[Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf)** — Review dependency-call behavior and retry amplification risks. Advanced; official PDF. Values require latency and failure evidence from your own system.

- **[Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/)** — Study duplicate-request handling and API design trade-offs. Advanced; operation semantics determine which retry behavior is safe.

- **[Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/)** — Review overload, feedback loops, and failure propagation. Advanced; validate containment strategies with bounded tests and measurements.

- **[OpenTelemetry Collector](https://opentelemetry.io/docs/collector/)** — Use the Collector model to discuss where telemetry is received, transformed, and exported, and who owns failures along that path. Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling.

- **[Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html)** — Explore security and reliability together in system design and operations. Advanced; openly readable. Examples require interpretation for your environment.

## Data recovery and infrastructure economics

Recovery design must account for data state and dependencies, not just redeployment. Cost design includes idle headroom, telemetry retention, build capacity, and the operational burden of the chosen components.

- **[Designing Data-Intensive Applications](https://dataintensive.net/)** — Martin Kleppmann’s Designing Data-Intensive Applications compares data-system concepts including replication, transactions, and distributed data processing. Commercial book; the public website is not the full text. Useful for reasoning about replication, transactions, and data-system tradeoffs.

- **[PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html)** — Review database backup approaches and their operational implications. Advanced; use documentation matching the deployed database version and test restored data.

- **[AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html)** — Compare recovery strategies and resilience considerations for AWS workloads. Advanced; define recovery time and recovery point objectives and test the complete workload.

- **[Azure reliability disaster-recovery guidance](https://learn.microsoft.com/en-us/azure/reliability/disaster-recovery-overview)** — Locate Azure disaster-recovery concepts and planning guidance. Advanced; service support and workload dependencies determine feasible recovery objectives.

- **[Google Cloud disaster recovery planning guide](https://cloud.google.com/architecture/dr-scenarios-planning-guide)** — Review recovery planning, objectives, and scenario selection. Advanced; test identity, configuration, data, and traffic restoration together.

- **[FinOps Framework](https://www.finops.org/framework/)** — Use the FinOps Foundation framework to include financial accountability and technology value in an architecture review. Intermediate; apply using actual operating and billing evidence.

- **[Infracost](https://www.infracost.io/docs/)** — Cost estimates and changes for supported infrastructure definitions before deployment. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees.

- **[OpenCost](https://opencost.io/docs/)** — Kubernetes cost allocation based on resource usage and pricing inputs. Intermediate; allocation assumptions, data quality, and shared costs need review.

## Use a reference without copying its assumptions

Record the workload, expected scale, failure domains, identity model, data requirements, operating team, and provider-specific dependencies. State what you adopted, what you changed, and the evidence you still need. Keep the original reference alongside your architecture decision record.

## Continue exploring

[Compare tools](devops-architect-tools-and-technologies.md) · [Find official references](devops-architect-official-documentation.md) · [Explore architecture resources](devops-architect-architecture-resources.md) · [Find practical projects](devops-architect-labs-and-portfolio-projects.md)

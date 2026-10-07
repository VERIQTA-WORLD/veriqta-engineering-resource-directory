# DevOps architect: role and responsibility resources

[DevOps architect resource directory](README.md)

Use these resources to understand the decisions a DevOps architect may help own and the evidence behind those decisions. The title varies by organization: architecture work may sit with senior DevOps engineers, platform architects, release engineers, or reliability teams. Treat the categories as responsibility areas, not a universal job description.

Your contribution is to make delivery and operations coherent across teams. The resources below connect that responsibility to research, design methods, implementation guidance, and operating practices.

## Find resources by topic

- [Understand delivery outcomes and constraints](#understand-delivery-outcomes-and-constraints)
- [Design ownership and collaboration boundaries](#design-ownership-and-collaboration-boundaries)
- [Make architecture decisions reviewable](#make-architecture-decisions-reviewable)
- [Establish delivery controls and artifact trust](#establish-delivery-controls-and-artifact-trust)
- [Specify production acceptance and recovery](#specify-production-acceptance-and-recovery)
- [Support platforms as usable services](#support-platforms-as-usable-services)
- [Manage cost and improvement over time](#manage-cost-and-improvement-over-time)

## Understand delivery outcomes and constraints

Start with how a change reaches users, what slows it down, and what makes it unsafe. Measure improvement at a meaningful service or team boundary, and include reliability alongside delivery speed.

- **[DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)** — Explains the practices and organizational conditions behind releasing software safely on demand. Public research-backed capability guide; use it to identify improvement hypotheses, not to choose a pipeline product.

- **[DORA: Software delivery performance metrics](https://dora.dev/guides/dora-metrics/)** — Explains delivery-performance measures and how to use them for improvement. Read definitions and measurement boundaries before comparing services; do not turn team measures into individual productivity scores.

- **[DORA Guides](https://dora.dev/guides/)** — Explore delivery measurement, value-stream analysis, and improvement guidance. Intermediate; use measures to investigate system behavior rather than rank individuals.

- **[Accelerate publisher page](https://itrevolution.com/product/accelerate/)** — IT Revolution’s publisher page for Accelerate by Nicole Forsgren, Jez Humble, and Gene Kim describes research on software delivery performance and the practices associated with it. Intermediate; paid book. Consider its research period alongside current DORA publications.

## Design ownership and collaboration boundaries

Identify who owns builds, runtime platforms, service behavior, production access, and recovery. Investigate dependencies that require teams to coordinate every release.

- **[DORA: Loosely coupled teams](https://dora.dev/capabilities/loosely-coupled-teams/)** — Connects independent delivery to team boundaries and software architecture. Useful when release coordination is a bottleneck; an organization chart alone cannot establish independent deployability.

- **[Team Topologies resources](https://teamtopologies.com/)** — Explore the authors' model for team boundaries and interaction modes. Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions.

- **[CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)** — Use the CNCF platform model to identify which shared capabilities need product, user, and operating ownership. Intermediate; platform design must start with developer and operator needs.

- **[Microsoft Engineering Playbook](https://microsoft.github.io/code-with-engineering-playbook/)** — Publishes engineering practices for design, testing, delivery, code review, and team collaboration. Public organizational playbook; adapt its practices to your context rather than treating one organization's process as universal.

## Make architecture decisions reviewable

Capture options, constraints, tradeoffs, consequences, and the conditions under which a decision should be revisited. Use diagrams at the level relevant to the discussion.

- **[Architecture Decision Records](https://adr.github.io/)** — Use decision-record formats to make architecture recommendations and their consequences reviewable by the people who must implement them. Foundation onward; keep decisions connected to evidence and later changes.

- **[C4 model](https://c4model.com/)** — Describe software systems at useful levels of architectural abstraction. Foundation onward; diagrams communicate structure but do not establish operational correctness.

- **[arc42 architecture documentation template](https://arc42.org/)** — Provides a structure for documenting goals, constraints, building blocks, quality requirements, decisions, and risks. Public template and examples; use the relevant sections instead of filling every heading mechanically.

- **[SEI: Architecture Tradeoff Analysis Method](https://www.sei.cmu.edu/library/the-architecture-tradeoff-analysis-method/)** — Introduces a structured method for evaluating architectural choices against quality attributes and stakeholder scenarios. Public SEI paper description and download route for the foundational method; detailed application requires preparation and stakeholder participation.

- **[Building Evolutionary Architectures](https://evolutionaryarchitecture.com/)** — Provides author-associated book information and supporting material on incremental architectural change and fitness functions. Commercial book with public supporting material; use it to think about keeping design constraints testable as systems change.

## Establish delivery controls and artifact trust

Connect approvals and policy to risk rather than adding handoffs indiscriminately. Be explicit about build identity, artifact evidence, deployment authority, and exceptions.

- **[GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions)** — Review runner trust, workflow access, and delivery credential exposure. Intermediate; public contributions and privileged jobs need distinct trust treatment.

- **[GitHub Actions: OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect)** — Explains federated workflow identity for obtaining short-lived credentials from supporting cloud providers. Public official concept guide; trust conditions still need to constrain repository, workflow, environment, and audience.

- **[GitHub Actions: Deployment environments](https://docs.github.com/en/actions/how-tos/deploy/configure-and-manage-deployments/manage-environments)** — Describes environment protection, deployment configuration, and environment secrets. Public official guide; feature availability depends on repository visibility and plan. Evaluate emergency access and approval ownership.

- **[SLSA specification](https://slsa.dev/spec/)** — Use the specification to assign responsibility for artifact provenance and the security guarantees expected of the build process. Advanced; consult the relevant stable version and track specification changes.

- **[NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final)** — Review secure development practices and their organizational integration. Intermediate to advanced; use the publication's stated scope and any applicable local requirements.

- **[OpenGitOps principles](https://opengitops.dev/)** — Use shared principles to discuss declarative state, version history, pull, and reconciliation. Intermediate; community principles. Evaluate whether the implementation meets them.

## Specify production acceptance and recovery

Define what must be true before a service is accepted into production, and what evidence shows it can be recovered. A deployment success signal is not the same as an acceptable user outcome.

- **[Implementing SLOs](https://sre.google/workbook/implementing-slos/)** — Review practical service-level objective design and adoption. Intermediate; useful measures depend on service behavior and user expectations.

- **[Canarying releases](https://sre.google/workbook/canarying-releases/)** — Review candidate evaluation, rollout design, and the limits of release signals. Advanced; comparison quality and observation design determine whether a canary is informative.

- **[Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf)** — Review compatibility and recovery concerns when versions coexist or change. Advanced; official PDF. Application and schema compatibility must be tested in your own system.

- **[AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html)** — Compare recovery strategies and resilience considerations for AWS workloads. Advanced; define recovery time and recovery point objectives and test the complete workload.

- **[PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html)** — Review database backup approaches and their operational implications. Advanced; use documentation matching the deployed database version and test restored data.

- **[Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html)** — Explore security and reliability together in system design and operations. Advanced; openly readable. Examples require interpretation for your environment.

## Support platforms as usable services

Examine whether platform users can perform routine work safely without waiting for a specialist. Document supported workflows, interfaces, limitations, and ownership rather than offering an unexplained collection of infrastructure components.

- **[Backstage Software Templates](https://backstage.io/docs/features/software-templates/)** — Explains template-based project scaffolding and the actions used to produce software repositories. Public project documentation; review action permissions and input handling rather than equating scaffolding with production readiness.

- **[Backstage](https://backstage.io/docs/overview/what-is-backstage/)** — A developer-portal framework with a software catalog, templates, and plugin integrations. Intermediate; catalog quality and plugin maintenance need ownership. A portal alone is not a complete platform.

## Manage cost and improvement over time

Review the cost of architecture choices, operating complexity, stale dependencies, and incident follow-up. Improvements should have an owner and a way to evaluate their effect.

- **[FinOps Framework](https://www.finops.org/framework/)** — Use the FinOps Foundation framework to connect architecture responsibilities with spending ownership and technology value. Intermediate; apply using actual operating and billing evidence.

- **[Infracost](https://www.infracost.io/docs/)** — Cost estimates and changes for supported infrastructure definitions before deployment. Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees.

- **[OpenCost](https://opencost.io/docs/)** — Kubernetes cost allocation based on resource usage and pricing inputs. Intermediate; allocation assumptions, data quality, and shared costs need review.

- **[Postmortem culture](https://sre.google/sre-book/postmortem-culture/)** — Review incident learning, documentation, and follow-up practices. Intermediate; focus on evidenced contributing factors and actionable improvement.

- **[Managing incidents](https://sre.google/sre-book/managing-incidents/)** — Review incident roles, coordination, communication, and operational response. Intermediate; adapt role separation to team size and actual on-call arrangements.

- **[AWS Well-Architected: Operational Excellence](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/welcome.html)** — Organizes operating-model, preparation, operations, and improvement guidance for AWS workloads. Public official pillar guide; adapt the questions to your ownership model and pair them with implementation evidence.

## Useful evidence to bring to a review

A delivery-path map, ownership matrix, decision records, a threat model, service objectives, a recovery design, and prioritized improvement hypotheses make these resources actionable. You do not need to own every component personally; you do need to make the boundaries and unresolved decisions visible.

## Continue exploring

[Compare tools](devops-architect-tools-and-technologies.md) · [Find official references](devops-architect-official-documentation.md) · [Explore architecture resources](devops-architect-architecture-resources.md) · [Find practical projects](devops-architect-labs-and-portfolio-projects.md)

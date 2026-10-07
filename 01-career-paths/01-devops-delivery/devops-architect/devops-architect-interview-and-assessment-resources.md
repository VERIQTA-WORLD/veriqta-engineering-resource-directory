# DevOps architect: interview and assessment resources

[DevOps architect resource directory](README.md)

Use these references to prepare evidence-based architecture discussions or design a fair technical assessment. You should be able to explain constraints, compare options, identify failure paths, and defend the evidence behind your decisions. Memorizing commands or product names does not demonstrate those abilities.

This page links public review methods, technical references, and official certification information. The practice prompts are original discussion exercises, not claimed employer questions, leaked examination content, or a universal hiring rubric.

## Find resources by topic

- [Architecture review methods and communication](#architecture-review-methods-and-communication)
- [Delivery design and organizational tradeoffs](#delivery-design-and-organizational-tradeoffs)
- [Deployment safety and runtime failure reasoning](#deployment-safety-and-runtime-failure-reasoning)
- [Identity policy and supply-chain assessment](#identity-policy-and-supply-chain-assessment)
- [Incident recovery and cost discussions](#incident-recovery-and-cost-discussions)
- [Official certification objectives and preparation discovery](#official-certification-objectives-and-preparation-discovery)

## Architecture review methods and communication

Prepare to turn an ambiguous requirement into a system boundary, quality scenarios, options, and a reasoned decision. Show what additional information could change your answer.

- **[SEI: Architecture Tradeoff Analysis Method](https://www.sei.cmu.edu/library/the-architecture-tradeoff-analysis-method/)** — Introduces a structured method for evaluating architectural choices against quality attributes and stakeholder scenarios. Public SEI paper description and download route for the foundational method; detailed application requires preparation and stakeholder participation.

- **[arc42 architecture documentation template](https://arc42.org/)** — Provides a structure for documenting goals, constraints, building blocks, quality requirements, decisions, and risks. Public template and examples; use the relevant sections instead of filling every heading mechanically.

- **[C4 model](https://c4model.com/)** — Use the diagramming model to practice showing scope and dependencies without relying on a wall of vendor icons. Foundation onward; diagrams communicate structure but do not establish operational correctness.

- **[Architecture Decision Records](https://adr.github.io/)** — Use decision-record examples to prepare a concise defense of a choice and the assumptions that could change it. Foundation onward; keep decisions connected to evidence and later changes.

- **[Fundamentals of Software Architecture](https://www.thoughtworks.com/en-us/insights/books/fundamentals-of-software-architecture)** — Introduces Mark Richards and Neal Ford's book about architecture characteristics, styles, and the architect's work. Public book description and related discussion; the book itself is commercial. Broader software architecture, not a DevOps implementation manual.

## Delivery design and organizational tradeoffs

Use these resources when discussing slow releases, integration risk, cross-team dependencies, and improvement measures. Explain the measurement boundary and what evidence would support a proposed change.

- **[DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)** — Explains the practices and organizational conditions behind releasing software safely on demand. Public research-backed capability guide; use it to identify improvement hypotheses, not to choose a pipeline product.

- **[DORA: Loosely coupled teams](https://dora.dev/capabilities/loosely-coupled-teams/)** — Connects independent delivery to team boundaries and software architecture. Useful when release coordination is a bottleneck; an organization chart alone cannot establish independent deployability.

- **[DORA: Software delivery performance metrics](https://dora.dev/guides/dora-metrics/)** — Explains delivery-performance measures and how to use them for improvement. Read definitions and measurement boundaries before comparing services; do not turn team measures into individual productivity scores.

- **[Martin Fowler: Continuous Integration](https://martinfowler.com/articles/continuousIntegration.html)** — Explains continuous integration practices, integration frequency, build feedback, and common misunderstandings. Public author article; use it to distinguish CI as a working practice from a server that happens to run builds.

- **[Team Topologies resources](https://teamtopologies.com/)** — Explore the authors' model for team boundaries and interaction modes. Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions.

## Deployment safety and runtime failure reasoning

Practice describing rollout success, rollback conditions, incompatible state changes, dependency failures, and overload. The references give you mechanisms and failure cases to reason about.

- **[Canarying releases](https://sre.google/workbook/canarying-releases/)** — Review candidate evaluation, rollout design, and the limits of release signals. Advanced; comparison quality and observation design determine whether a canary is informative.

- **[Ensuring rollback safety during deployments](https://d1.awsstatic.com/builderslibrary/pdfs/ensuring-rollback-safety-during-deployments.pdf)** — Review compatibility and recovery concerns when versions coexist or change. Advanced; official PDF. Application and schema compatibility must be tested in your own system.

- **[Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf)** — Review dependency-call behavior and retry amplification risks. Advanced; official PDF. Values require latency and failure evidence from your own system.

- **[Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/)** — Study duplicate-request handling and API design trade-offs. Advanced; operation semantics determine which retry behavior is safe.

- **[Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/)** — Review overload, feedback loops, and failure propagation. Advanced; validate containment strategies with bounded tests and measurements.

- **[Implementing SLOs](https://sre.google/workbook/implementing-slos/)** — Review practical service-level objective design and adoption. Intermediate; useful measures depend on service behavior and user expectations.

## Identity policy and supply-chain assessment

Be ready to identify the principal, resource, trust boundary, and permitted action in a deployment path. Explain what a signature, provenance record, scan result, or approval does and does not prove.

- **[GitHub Actions: OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect)** — Explains federated workflow identity for obtaining short-lived credentials from supporting cloud providers. Public official concept guide; trust conditions still need to constrain repository, workflow, environment, and audience.

- **[GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions)** — Review runner trust, workflow access, and delivery credential exposure. Intermediate; public contributions and privileged jobs need distinct trust treatment.

- **[SLSA specification](https://slsa.dev/spec/)** — Use the specification to check whether you can explain the difference between artifact metadata and a verified build guarantee. Advanced; consult the relevant stable version and track specification changes.

- **[NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final)** — Review secure development practices and their organizational integration. Intermediate to advanced; use the publication's stated scope and any applicable local requirements.

- **[OWASP Threat Modeling](https://owasp.org/www-community/Threat_Modeling)** — Explains threat-modeling activities and questions for identifying design risks and mitigations. Public community guidance; review actual assets, trust boundaries, attack paths, and assumptions for your system.

## Incident recovery and cost discussions

Explain how you would assess a backup, diagnose a failed restoration, or choose resilience within a budget. Separate evidence from guesses about a historical incident.

- **[PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html)** — Review database backup approaches and their operational implications. Advanced; use documentation matching the deployed database version and test restored data.

- **[AWS disaster recovery guidance](https://docs.aws.amazon.com/whitepapers/latest/disaster-recovery-workloads-on-aws/disaster-recovery-workloads-on-aws.html)** — Compare recovery strategies and resilience considerations for AWS workloads. Advanced; define recovery time and recovery point objectives and test the complete workload.

- **[FinOps Framework](https://www.finops.org/framework/)** — Use the FinOps Foundation framework to structure a discussion of cost ownership, value, and operating tradeoffs. Intermediate; apply using actual operating and billing evidence.

- **[Cloudflare outage report, July 2019](https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/)** — Study an original account of a software change, resource exhaustion, and recovery. Advanced; historical incident, not a description of the company's current architecture.

- **[GitLab database outage report, January 2017](https://about.gitlab.com/blog/2017/02/01/gitlab-dot-com-database-incident/)** — Study an original recovery incident and the importance of tested backup procedures. Advanced; historical incident. Distinguish recorded facts from assumptions about present systems.

## Official certification objectives and preparation discovery

Use exam objectives to locate knowledge gaps if the credential is relevant to your work. Certification requirements are provider-specific, change over time, and do not assess every DevOps architecture responsibility.

- **[AWS Certified Solutions Architect Associate](https://aws.amazon.com/certification/certified-solutions-architect-associate/)** — Describes an AWS architecture certification and official preparation entry points. Provider-specific certification information, not proof of DevOps architecture competence; exam registration and training may incur separate costs.

- **[Microsoft Certified DevOps Engineer Expert](https://learn.microsoft.com/en-us/credentials/certifications/devops-engineer/)** — Describes Microsoft's DevOps certification requirements and official preparation routes. Certification discovery; check current prerequisites and exam requirements. A credential does not replace design or production evidence.

- **[Google Cloud Professional Cloud DevOps Engineer](https://cloud.google.com/learn/certification/cloud-devops-engineer)** — Describes the provider's DevOps certification focus and preparation resources. Provider-specific exam information; review current objectives and exam terms, not generic interview-question claims.

- **[CNCF Training and Certification](https://www.cncf.io/training/certification/)** — Lists cloud-native certifications and provider training routes. Certification discovery; exams are separate from free documentation and scope varies by credential.

## Practice architecture discussions

Use a disposable sample system or a sanitized diagram from your own work. The prompts below are practice suggestions, not procedures to run against production.

| Situation | Discuss | Bring evidence |
| --- | --- | --- |
| A pipeline succeeds while users receive errors | Distinguish build, deployment, release, and user outcomes; choose acceptance signals and abort conditions | A delivery-path diagram and a canary decision with measurable criteria |
| Every team must release together | Identify application, data, infrastructure, and organizational coupling; compare incremental changes | A dependency map and a decision record showing a small first improvement |
| A build runner is compromised | Trace credentials, artifacts, signing authority, network reach, and promotion rights | A trust-boundary model and a containment/recovery proposal |
| An infrastructure plan would replace a shared service | Explain state ownership, lifecycle effects, permissions, review, and recovery | A sanitized plan review and the assumptions needed before approval |
| A release changes both code and database structure | Compare compatibility windows and forward recovery with rollback | An old/new compatibility matrix and a release decision record |
| A dependency becomes slow and retries increase | Explain deadlines, retry amplification, idempotency, and load shedding | A request-path model and a bounded test proposal |
| A restore cannot meet the stated recovery objective | Consider data loss, dependency order, privileges, capacity, and integrity | A recovery design and a record of what has and has not been tested |
| Several teams want a shared platform | Compare supported user workflows, ownership, isolation, product needs, and operating cost | A platform boundary and evidence needed to test its usefulness |

## Assess reasoning consistently

Use the same constraints and follow-up opportunities for everyone being assessed. Let people name assumptions and ask questions before judging a design. Tools may differ while the underlying reasoning remains sound.

For each discussion, evaluate problem framing, technical correctness, alternatives and tradeoffs, failure and recovery reasoning, security boundaries, verification evidence, and clarity. A response that names an option is weaker than one that explains its fit and failure conditions. A strong response makes uncertainty visible and proposes a realistic way to reduce it.

If you use a score, define the scale before the session. For example: 0 means no usable reasoning; 1 identifies the concern; 2 explains a plausible mechanism; 3 connects the mechanism to constraints and alternatives; 4 adds meaningful verification and recovery evidence. This is an editorial suggestion, not a validated hiring instrument. Avoid inferring personal experience from confidence, accent, or familiarity with one vendor.

## Continue exploring

[Compare tools](devops-architect-tools-and-technologies.md) · [Find official references](devops-architect-official-documentation.md) · [Explore architecture resources](devops-architect-architecture-resources.md) · [Find practical projects](devops-architect-labs-and-portfolio-projects.md)

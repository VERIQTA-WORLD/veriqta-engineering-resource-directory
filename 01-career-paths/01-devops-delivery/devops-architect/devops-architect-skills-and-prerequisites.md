# DevOps architect: skills and prerequisite resources

[DevOps architect resource directory](README.md)

Use this page to find resources for a specific knowledge gap before you evaluate or design a delivery system. You do not need to finish these topics in a prescribed order. Start where your current design question exposes an assumption you cannot yet explain.

Foundation resources introduce operating-system, network, and development concepts. Implementation references assume you can already build or operate the component. Advanced architecture material assumes experience reasoning about failures, constraints, and tradeoffs.

## Find resources by topic

- [Linux shell processes and everyday engineering tools](#linux-shell-processes-and-everyday-engineering-tools)
- [Networking protocols and request paths](#networking-protocols-and-request-paths)
- [Programming integration and automated feedback](#programming-integration-and-automated-feedback)
- [Infrastructure state and desired-state reconciliation](#infrastructure-state-and-desired-state-reconciliation)
- [Containers scheduling and workload isolation](#containers-scheduling-and-workload-isolation)
- [Identity authorization and software trust](#identity-authorization-and-software-trust)
- [Reliability data and distributed-systems reasoning](#reliability-data-and-distributed-systems-reasoning)
- [Architecture communication teams and cost](#architecture-communication-teams-and-cost)

## Linux shell processes and everyday engineering tools

You should be able to explain a process, file permission, environment variable, exit status, and network listener before interpreting an automation failure. Practice with systems you can safely inspect and reset.

- **[Linux Journey](https://linuxjourney.com/)** — Offers short lessons on shell use, processes, permissions, filesystems, and networking. Public introductory lessons originally created by Cindy Quach; the reviewed destination redirects to the official Linux Journey page on LabEx. Hosted practice features may have separate access conditions.

- **[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/)** — MIT-hosted course material on shell tools, version control, debugging, profiling, and automation. Public lectures and exercises; this fills command-line workflow gaps rather than teaching a complete DevOps architecture.

- **[Pro Git](https://git-scm.com/book/en/v2)** — Strengthen understanding of Git behavior, collaboration, and repository workflows. Foundation to intermediate; openly readable. Practice with disposable repositories.

- **[Git](https://git-scm.com/docs)** — Use the reference when you cannot yet explain a branch, merge, commit, or history operation behind a delivery workflow. Foundation onward; a version-control tool, not a hosted collaboration platform.

## Networking protocols and request paths

Trace name resolution, connection establishment, encryption, proxies, and service responses. Distinguish an unreachable host, failed TLS negotiation, rejected authentication, and an application error.

- **[Beej's Guide to Network Programming](https://beej.us/guide/bgnet/)** — Explains sockets and network programming with worked examples. Public author-maintained guide; assumes programming knowledge and helps you understand connections below an application framework.

- **[HTTP semantics, RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html)** — Review method semantics, status codes, and HTTP behavior relevant to APIs and proxies. Intermediate to advanced; protocol semantics do not define your application's retry or authorization policy.

- **[TLS 1.3, RFC 8446](https://www.rfc-editor.org/info/rfc8446/)** — Review transport-security protocol requirements and behavior. Advanced; certificate lifecycle and application configuration require additional guidance.

- **[Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/)** — Inspect capture and protocol-analysis workflows for network diagnosis. Intermediate; use packet captures only where authorized. Captures can expose credentials and personal or customer data; the retrieved guide identifies a development build.

- **[Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api)** — Compare Kubernetes traffic-routing APIs and implementation support. Intermediate; APIs require a compatible implementation. Check conformance and feature status.

## Programming integration and automated feedback

Understand version control, executable build definitions, automated tests, repeatable environments, and error handling. Architecture work benefits from being able to inspect and change the code that implements a workflow.

- **[Martin Fowler: Continuous Integration](https://martinfowler.com/articles/continuousIntegration.html)** — Explains continuous integration practices, integration frequency, build feedback, and common misunderstandings. Public author article; use it to distinguish CI as a working practice from a server that happens to run builds.

- **[Testcontainers](https://testcontainers.com/guides/)** — Find guides for container-backed integration test dependencies. Intermediate; runtime and language-library requirements vary. Tests still need meaningful assertions.

- **[Bazel](https://bazel.build/about/intro)** — Review a build system's dependency model, rules, caching, and execution guidance. Advanced; adoption depends on language rules and integration effort. Caching alone does not establish reproducibility.

- **[Apache Maven](https://maven.apache.org/guides/)** — Review build and dependency-management guidance for Maven-based projects. Intermediate; assess plugin, repository, dependency, and credential governance.

## Infrastructure state and desired-state reconciliation

Explain what owns a resource, how drift is detected, and what happens after a partial failure. A plan, a configuration file, and a reconciler’s current status describe different states.

- **[Terraform state](https://developer.hashicorp.com/terraform/language/state)** — Learn why Terraform needs a mapping between configuration and existing resources before reasoning about drift, migration, or replacement. Intermediate; state may contain sensitive data. Protect storage and recovery procedures.

- **[Terraform backends](https://developer.hashicorp.com/terraform/language/backend)** — Compare state-backend configuration and documented backend capabilities. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike.

- **[Terraform testing](https://developer.hashicorp.com/terraform/language/tests)** — Review native test structures for modules and infrastructure workflows. Intermediate; some test arrangements create resources. Read execution and cleanup behavior first.

- **[OpenTofu](https://opentofu.org/docs/)** — A declarative infrastructure engine with provider configuration, planning, and state workflows. Compare its own documentation and compatibility requirements before a migration. Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability.

- **[Pulumi IaC](https://www.pulumi.com/docs/iac/)** — Infrastructure definitions using supported programming languages, with an engine that tracks deployments and resource state. Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies.

- **[Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html)** — Agentless configuration and orchestration through inventories, modules, and playbooks. Intermediate; idempotency depends on modules and task design. Check collection and target compatibility.

- **[OpenGitOps principles](https://opengitops.dev/)** — Read the principles to distinguish declared and versioned desired state from a script that merely deploys from a repository. Intermediate; community principles. Evaluate whether the implementation meets them.

## Containers scheduling and workload isolation

Understand image construction and runtime behavior before choosing an orchestrator. For Kubernetes, connect authorization, resource scheduling, network access, disruptions, and application health.

- **[Docker workshop](https://docs.docker.com/get-started/workshop/)** — Walks through building, running, sharing, and extending a containerized application. Foundation practice; requires a suitable container environment. Images, volumes, ports, and local resources need cleanup after experiments.

- **[containerd](https://containerd.io/docs/)** — A container runtime managing image transfer, storage, execution, and runtime lifecycle below an orchestrator. Advanced; primarily runtime and node architecture. It does not replace a delivery platform.

- **[Container resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/)** — Review requests, limits, scheduling, and resource constraints. Intermediate; workload measurements and node capacity are needed for useful settings.

- **[Liveness, readiness, and startup probes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)** — Review health-check semantics and configuration. Intermediate; unsuitable checks can cause restart loops or hide unavailable dependencies.

- **[Kubernetes multi-tenancy](https://kubernetes.io/docs/concepts/security/multi-tenancy/)** — Review isolation choices and their limitations. Advanced; namespaces alone do not provide every required isolation boundary.

- **[Kubernetes RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)** — Design role-based access control for users, workloads, and controllers. Intermediate; assess escalation paths, broad grants, and service-account use.

- **[Kubernetes NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/network-policies/)** — Review traffic-control semantics and policy examples. Intermediate; enforcement depends on the network implementation and its supported behavior.

## Identity authorization and software trust

Separate authentication from authorization and artifact authenticity from vulnerability status. Explain where credentials originate, how they expire, and which principal can change production.

- **[OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html)** — Review identity-layer protocol requirements and flows. Advanced; distinguish authentication from resource authorization and verify implementation guidance.

- **[OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700.html)** — Review current protocol security recommendations for OAuth implementations. Advanced; applies alongside the relevant OAuth specifications and implementation documentation.

- **[GitHub Actions: OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect)** — Learn how a workflow requests short-lived provider credentials and why the trust relationship needs restrictive conditions. Public official concept guide; trust conditions still need to constrain repository, workflow, environment, and audience.

- **[SPIFFE](https://spiffe.io/docs/latest/spiffe-about/overview/)** — Workload identity specifications and concepts for identifying services across trust domains. Advanced; workload identity complements rather than replaces application authorization.

- **[SLSA specification](https://slsa.dev/spec/)** — Review software supply-chain assurance and provenance requirements. Advanced; consult the relevant stable version and track specification changes.

- **[NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final)** — Review secure development practices and their organizational integration. Intermediate to advanced; use the publication's stated scope and any applicable local requirements.

- **[OWASP Threat Modeling](https://owasp.org/www-community/Threat_Modeling)** — Explains threat-modeling activities and questions for identifying design risks and mitigations. Public community guidance; review actual assets, trust boundaries, attack paths, and assumptions for your system.

## Reliability data and distributed-systems reasoning

Be able to discuss consistency, replication, dependency failure, overload, retry amplification, and recovery objectives. Distributed-system theory helps you recognize limits that another retry cannot fix.

- **[Designing Data-Intensive Applications](https://dataintensive.net/)** — Martin Kleppmann’s Designing Data-Intensive Applications compares data-system concepts including replication, transactions, and distributed data processing. Commercial book; the public website is not the full text. Useful for reasoning about replication, transactions, and data-system tradeoffs.

- **[MIT Distributed Systems course](https://pdos.csail.mit.edu/6.824/)** — Publishes distributed-systems readings, lectures, and programming-lab information. Advanced academic material; substantial programming and concurrency knowledge are assumed. Check the linked course year's requirements.

- **[Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/)** — Read original material on service objectives, risk, toil, monitoring, and operational engineering. Intermediate; openly readable. Translate examples to your team size and system constraints.

- **[Implementing SLOs](https://sre.google/workbook/implementing-slos/)** — Review practical service-level objective design and adoption. Intermediate; useful measures depend on service behavior and user expectations.

- **[Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf)** — Review dependency-call behavior and retry amplification risks. Advanced; official PDF. Values require latency and failure evidence from your own system.

- **[Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/)** — Study duplicate-request handling and API design trade-offs. Advanced; operation semantics determine which retry behavior is safe.

- **[Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/)** — Review overload, feedback loops, and failure propagation. Advanced; validate containment strategies with bounded tests and measurements.

- **[PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html)** — Review database backup approaches and their operational implications. Advanced; use documentation matching the deployed database version and test restored data.

## Architecture communication teams and cost

Architecture includes negotiation and evidence, not only diagrams. Learn to state constraints, compare options, write decisions, work across ownership boundaries, and explain the economics of a design.

- **[C4 model](https://c4model.com/)** — Learn to communicate the system boundary before adding implementation details to a diagram. Foundation onward; diagrams communicate structure but do not establish operational correctness.

- **[Architecture Decision Records](https://adr.github.io/)** — Find guidance and resources for recording architectural decisions. Foundation onward; keep decisions connected to evidence and later changes.

- **[arc42 architecture documentation template](https://arc42.org/)** — Provides a structure for documenting goals, constraints, building blocks, quality requirements, decisions, and risks. Public template and examples; use the relevant sections instead of filling every heading mechanically.

- **[Fundamentals of Software Architecture](https://www.thoughtworks.com/en-us/insights/books/fundamentals-of-software-architecture)** — Introduces Mark Richards and Neal Ford's book about architecture characteristics, styles, and the architect's work. Public book description and related discussion; the book itself is commercial. Broader software architecture, not a DevOps implementation manual.

- **[Team Topologies resources](https://teamtopologies.com/)** — Explore the authors' model for team boundaries and interaction modes. Intermediate; organizational guidance requires local adaptation. Books and training have separate access conditions.

- **[FinOps Framework](https://www.finops.org/framework/)** — Explore cost ownership and technology-value concepts before treating an infrastructure estimate as a full economic decision. Intermediate; apply using actual operating and billing evidence.

- **[DORA: Software delivery performance metrics](https://dora.dev/guides/dora-metrics/)** — Explains delivery-performance measures and how to use them for improvement. Read definitions and measurement boundaries before comparing services; do not turn team measures into individual productivity scores.

## Check a gap with evidence

Pick a system you know and explain its change path, request path, identities, data state, main failure domains, observability, and recovery. Mark the points you cannot explain, then choose the corresponding resource group. This is a self-assessment aid, not a certification checklist.

## Continue exploring

[Compare tools](devops-architect-tools-and-technologies.md) · [Find official references](devops-architect-official-documentation.md) · [Explore architecture resources](devops-architect-architecture-resources.md) · [Find practical projects](devops-architect-labs-and-portfolio-projects.md)

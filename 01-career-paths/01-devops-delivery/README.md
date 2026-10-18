# DevOps Delivery: Career and Engineering Resource Directory

Find resources for the work that turns software changes into usable, supportable services. Choose a responsibility below, then use its documentation, architecture, learning, practice, and assessment pages to answer a concrete engineering question.

Choose a role according to the responsibility you need to understand. Titles vary between organizations; use the engineering task to guide your reading.

## Choose a responsibility

| Role | Focus | Useful first question |
| --- | --- | --- |
| [DevOps Architect](devops-architect/README.md) | Designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership | Which boundaries and controls let teams release independently without losing operating accountability? |
| [DevOps Automation Engineer](devops-automation-engineer/README.md) | Turning repeated engineering tasks into bounded, observable workflows with explicit inputs and failure behavior | What happens when an operation is retried after only part of it completed? |
| [DevOps Consultant](devops-consultant/README.md) | Assessing delivery constraints, testing improvement hypotheses, and transferring usable capabilities to client teams | Which change addresses the demonstrated constraint, and what evidence would show it helped? |
| [DevOps Engineer](devops-engineer/README.md) | Implementing and operating the path from source changes to usable services | Can you trace the deployed artifact to its source and establish whether users can use it? |
| [DevOps Infrastructure Engineer](devops-infrastructure-engineer/README.md) | Building and maintaining the compute, networking, identity, configuration, and state foundations behind software delivery | Can you change or rebuild infrastructure without losing control of state, access, data, and recovery? |
| [DevOps Platform Engineer](devops-platform-engineer/README.md) | Providing supported delivery capabilities that other engineers can use through predictable interfaces | Can a team complete a supported workflow and recover from failure without depending on undocumented platform knowledge? |

## Choose by the problem

- **Delivery succeeds but the application fails:** Start with DevOps Engineer production practices and troubleshooting references.
- **Repeated operations duplicate work or leave uncertain results:** Start with DevOps Automation Engineer architecture and official documentation.
- **The client requests a tool before the constraint is clear:** Start with DevOps Consultant responsibilities and assessment methods.
- **Shared resource changes are hard to coordinate or recover:** Start with DevOps Infrastructure Engineer state and lifecycle resources.
- **Several teams need a supported delivery capability:** Start with DevOps Platform Engineer contracts, permissions, and consumer evidence.
- **Cross-system decisions need coherent boundaries and trade-offs:** Start with DevOps Architect architecture resources.

## Use the collections together

A responsibility can move between collections as work develops. An assessment may identify a workflow problem; architecture establishes the boundaries; automation implements repeatable operations; infrastructure provides controlled resources; delivery engineering verifies the service; platform engineering exposes a supported shared capability. The order depends on the actual constraint and ownership.

Each role connects you to responsibility guides, technical references, architecture resources, operating practices, projects, and assessment questions. Use the project briefs to define your deliverables and the assessment questions to practise your reasoning.

## Primary reference directory

The annotations below provide a single maintained home for shared source descriptions, access conditions, and limitations. Role pages select relevant references and supply distinct engineering context. Sources are linked to their original publishers or maintainers. An entry labeled a specification or framework should be used within its stated scope, not as proof that a local implementation satisfies it.

<a id="source-dora"></a>

### [DORA: Continuous delivery](https://dora.dev/capabilities/continuous-delivery/)

DORA connects delivery capability to technical practices and organizational conditions.

- **Best for:** Familiarity with a software change moving through a team.
- **Start with:** Implementing continuous delivery and common pitfalls.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Research guidance does not prescribe a pipeline product or guarantee local outcomes.

<a id="source-metrics"></a>

### [DORA: Software delivery performance metrics](https://dora.dev/guides/dora-metrics/)

DORA explains measures for examining software delivery performance.

- **Best for:** A service boundary and accessible change records.
- **Start with:** Definitions and measurement boundaries.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Local event quality and definitions affect comparisons; team measures should not become individual quotas.

<a id="source-c4"></a>

### [C4 model](https://c4model.com/)

Simon Brown's C4 model provides levels of abstraction for communicating software architecture.

- **Best for:** Knowledge of the system and its dependencies.
- **Start with:** System context, then container diagrams when more detail is needed.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A structural diagram does not establish runtime behavior or recovery correctness.

<a id="source-adr"></a>

### [Architecture Decision Records](https://adr.github.io/)

This community-maintained directory collects decision-record guidance and formats.

- **Best for:** A decision with real alternatives and consequences.
- **Start with:** The introductory explanation and a suitable template.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A recorded preference needs evidence and later review; a template cannot supply them.

<a id="source-arc"></a>

### [arc42](https://arc42.org/)

The arc42 project offers a structure for architecture documentation.

- **Best for:** An identifiable system boundary and stakeholders.
- **Start with:** The template overview and quality requirements.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Select useful sections; filling every section is not proof of design quality.

<a id="source-platforms"></a>

### [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)

CNCF TAG App Delivery discusses platforms, their users, and organizational context.

- **Best for:** Experience with developer workflows and operations.
- **Start with:** Platform capabilities and the platform-as-product discussion.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A capability model must be adapted to local needs and operating capacity.

<a id="source-actions"></a>

### [GitHub Actions documentation](https://docs.github.com/en/actions)

GitHub documents workflow concepts, implementation, and operating features.

- **Best for:** Git and repository workflow familiarity.
- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Hosted usage, feature availability, and runner responsibility depend on the account and configuration.

<a id="source-secure"></a>

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

GitHub describes security considerations for workflow execution and dependencies.

- **Best for:** Understanding of triggers, jobs, and runner access.
- **Start with:** Untrusted input, credentials, and third-party actions.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A secure-use review must include your actual integrations and trust boundaries.

<a id="source-reuse"></a>

### [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows)

GitHub explains calling and maintaining reusable workflows.

- **Best for:** Working knowledge of a basic workflow.
- **Start with:** Inputs, secrets, permissions, and version references.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Sharing execution logic also creates compatibility and rollout responsibilities.

<a id="source-env"></a>

### [GitHub Actions: Deployment environments](https://docs.github.com/en/actions/concepts/workflows-and-actions/deployment-environments)

GitHub introduces environments for deployment-related configuration and protection.

- **Best for:** A repository and a deployment workflow.
- **Start with:** The environment concept and linked configuration guidance.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Protection features depend on repository and account conditions; confirm support before relying on them.

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

<a id="source-tests"></a>

### [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests)

HashiCorp documents Terraform test configuration and execution.

- **Best for:** Compatible Terraform version and provider prerequisites.
- **Start with:** Test files, run blocks, and assertions.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Some test paths create real infrastructure; inspect execution and cleanup behavior.

<a id="source-tf-lab"></a>

### [Terraform Docker tutorial collection](https://developer.hashicorp.com/terraform/tutorials/docker-get-started)

HashiCorp provides guided Terraform learning using a local Docker environment.

- **Best for:** Terraform, Docker, and a suitable local machine.
- **Start with:** Prerequisites, infrastructure lifecycle, and destroy instructions.
- **Access:** Free public tutorials; local software requirements apply.
- **Important limit:** This local provider exercise does not reproduce cloud IAM, networking, or availability.

<a id="source-ansible"></a>

### [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html)

Ansible documents playbook concepts and task organization.

- **Best for:** Inventory, managed-host access, and configuration-management basics.
- **Start with:** Playbook execution and desired-state task structure.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Idempotence depends on the modules and tasks you write; do not assume every action is repeatable.

<a id="source-check"></a>

### [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html)

Ansible explains preview-oriented execution and configuration differences.

- **Best for:** A known inventory and compatible tasks.
- **Start with:** Module support and the limitations of check mode.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Preview support varies, and diff output can reveal sensitive content.

<a id="source-python"></a>

### [Python subprocess reference](https://docs.python.org/3/library/subprocess.html)

The Python standard-library reference describes process execution and result handling.

- **Best for:** Basic Python and process/exit-status knowledge.
- **Start with:** Frequently used arguments and security considerations.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Shell interpretation and process side effects need deliberate control; select your Python version.

<a id="source-systemd"></a>

### [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html)

The systemd project documents service-unit behavior and configuration.

- **Best for:** Linux service administration and the installed systemd version.
- **Start with:** Service type, process startup, and restart behavior.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Distribution versions and overrides can differ from the latest online manual.

<a id="source-kube"></a>

### [Kubernetes overview](https://kubernetes.io/docs/concepts/overview/)

The Kubernetes project introduces its orchestration model and purpose.

- **Best for:** Containers, basic networking, and application configuration.
- **Start with:** What Kubernetes does and the linked concepts.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** The overview is conceptual; operating decisions need task-specific and version-matched references.

<a id="source-debug"></a>

### [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/)

The Kubernetes project organizes application diagnostic references.

- **Best for:** Workload, Service, and namespace familiarity.
- **Start with:** The guide matching the failing application boundary.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A symptom requires local evidence; a diagnostic catalog does not establish its cause.

<a id="source-kind"></a>

### [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/)

The kind project documents local Kubernetes cluster creation and deletion.

- **Best for:** A supported container runtime, local capacity, and compatible tools.
- **Start with:** Installation, creating a cluster, interacting with it, and deletion.
- **Access:** Free public guide; local software and machine resources are required.
- **Important limit:** Local clusters do not model every cloud load balancer, storage system, or failure domain.

<a id="source-docker"></a>

### [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/)

Docker provides a guided container application example with cleanup.

- **Best for:** Docker software, Git, and the account requirements in the guide.
- **Start with:** Before you start, then the application workflow.
- **Access:** Free public guide; software licensing and account requirements are separate.
- **Important limit:** Registry publication can expose content; use synthetic applications and inspect licensing.

<a id="source-argo"></a>

### [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/)

The Argo project documents declarative application delivery for Kubernetes.

- **Best for:** Kubernetes resources, Git, and application deployment knowledge.
- **Start with:** Core concepts, then the relevant user guide.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Reconciliation authority and deletion behavior need explicit review before enabling automation.

<a id="source-catalog"></a>

### [Backstage Software Catalog](https://backstage.io/docs/features/software-catalog/)

Backstage documents its software catalog and metadata model.

- **Best for:** Application-development familiarity and an appropriate Backstage environment.
- **Start with:** Entity concepts and ownership information.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Catalog metadata can be stale and is not an authorization system.

<a id="source-templates"></a>

### [Backstage Software Templates](https://backstage.io/docs/features/software-templates/)

Backstage documents scaffolding workflows for generating software components.

- **Best for:** A configured Backstage environment and integration knowledge.
- **Start with:** Template structure and available actions.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Actions can change external systems; review inputs, identity, and permissions.

<a id="source-permissions"></a>

### [Backstage permissions overview](https://backstage.io/docs/permissions/overview/)

Backstage introduces permission framework concepts and integration.

- **Best for:** Backend development and authentication familiarity.
- **Start with:** Permission concepts and policy integration.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Each plugin and downstream action needs appropriate enforcement; UI visibility alone is insufficient.

<a id="source-auth"></a>

### [Backstage authentication](https://backstage.io/docs/auth/)

Backstage documents authentication providers and identity integration.

- **Best for:** Identity-provider and backend configuration familiarity.
- **Start with:** Authentication architecture and your selected provider.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Authentication does not by itself define authorization for catalog or scaffolder actions.

<a id="source-sre"></a>

### [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)

Google publishes reliability practices and case studies in a freely readable workbook.

- **Best for:** Experience operating a service.
- **Start with:** The chapter corresponding to your current service concern.
- **Access:** Free online book; reading does not require a cloud account.
- **Important limit:** Examples reflect particular organizational settings; adapt staffing and scale assumptions.

<a id="source-slo"></a>

### [Implementing SLOs](https://sre.google/workbook/implementing-slos/)

Google's workbook discusses service-level objectives and their implementation.

- **Best for:** Understanding of user-visible service behavior.
- **Start with:** Selecting indicators, targets, and the improvement process.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Targets require product and operational judgment; example values are not universal requirements.

<a id="source-canary"></a>

### [Canarying Releases](https://sre.google/workbook/canarying-releases/)

Google's workbook examines canary release evaluation.

- **Best for:** Deployment and service-observability familiarity.
- **Start with:** Canary design, comparison signals, and decision criteria.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A small cohort with poor signal coverage can miss important failures.

<a id="source-incident"></a>

### [Incident Response](https://sre.google/workbook/incident-response/)

Google's workbook discusses organized incident response through examples.

- **Best for:** Understanding of service ownership and operational impact.
- **Start with:** Coordination, roles, communication, and follow-up.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Local escalation and authority arrangements must be explicit.

<a id="source-otel"></a>

### [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/)

OpenTelemetry explains the telemetry signals used to describe system behavior.

- **Best for:** Basic distributed application and observability concepts.
- **Start with:** Signals relevant to your diagnostic question.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Instrumentation does not automatically supply storage, retention, or an actionable alert.

<a id="source-alerts"></a>

### [Prometheus alerting practices](https://prometheus.io/docs/practices/alerting/)

Prometheus offers guidance on useful alerting.

- **Best for:** Metrics and service-operation familiarity.
- **Start with:** Symptom-oriented alerting and response relevance.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A rule needs validation against traffic, data quality, and an accountable responder.

<a id="source-aws"></a>

### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

AWS offers a framework for examining workload design and operation.

- **Best for:** A defined workload and stakeholder requirements.
- **Start with:** The framework overview and the pillar relevant to your review.
- **Access:** Free public reading; deploying AWS resources can incur charges.
- **Important limit:** AWS guidance is provider-specific and does not replace a workload-level validation.

<a id="source-iam"></a>

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

AWS describes the policy and permission model used to control access.

- **Best for:** AWS identities, resources, and basic JSON familiarity.
- **Start with:** Policy types and the linked evaluation guidance.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Assess all applicable policy layers; one policy document is not the complete effective permission set.

<a id="source-slsa"></a>

### [SLSA specification](https://slsa.dev/spec/)

SLSA defines a framework for describing software supply-chain assurance.

- **Best for:** Build systems and artifact trust concepts.
- **Start with:** Threats, tracks, and provenance concepts in the selected specification version.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** Provenance is evidence about origin and process, not proof that an artifact is harmless.

<a id="source-ssdf"></a>

### [NIST SP 800-218: Secure Software Development Framework](https://csrc.nist.gov/pubs/sp/800/218/final)

NIST publishes secure software development recommendations and associated practices.

- **Best for:** Software lifecycle and security responsibility awareness.
- **Start with:** Publication scope and the practice groups relevant to your assessment.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** This publication does not certify your implementation or establish every applicable obligation.

<a id="source-finops"></a>

### [FinOps Framework](https://www.finops.org/framework/)

The FinOps Foundation organizes technology-value and cost-management capabilities.

- **Best for:** Access to relevant usage, ownership, and billing context.
- **Start with:** Scope, allocation, ownership, and improvement capabilities.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A resource reduction can harm reliability; evaluate economics with operating requirements.

<a id="source-git"></a>

### [Pro Git, second edition](https://git-scm.com/book/en/v2)

Scott Chacon and Ben Straub explain Git concepts and workflows.

- **Best for:** Basic command-line familiarity.
- **Start with:** Git Basics, then branching and the internals relevant to your question.
- **Access:** Free online book; local exercises require Git.
- **Important limit:** Git does not define every hosting platform's approvals, identity, or workflow execution.

<a id="source-opa"></a>

### [OPA policy language](https://www.openpolicyagent.org/docs/policy-language)

Open Policy Agent documents Rego and policy evaluation.

- **Best for:** Structured data and basic authorization concepts.
- **Start with:** Language examples, input documents, and rule evaluation.
- **Access:** Free public reading; execution prerequisites and service charges are separate.
- **Important limit:** A policy decision needs an enforcement component; missing input and exceptions need tests.

## Improve a resource

Use the [repository contribution guide](../../CONTRIBUTING.md) to propose a precise correction. Include the affected page, current source destination, the issue, and how you verified it. Attribute original material and remove private data from examples. 

[All career paths](../README.md) · [Start Here](../../00-start-here/README.md) · [Engineering directory](../../README.md)

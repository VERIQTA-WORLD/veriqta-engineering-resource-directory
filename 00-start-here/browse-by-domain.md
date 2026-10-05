# Browse by domain

A technical domain is an area of engineering knowledge, such as networking, storage, delivery, or reliability. Browse by domain when you need to understand the mechanism behind a tool, fill a prerequisite gap, or study a discipline beyond one implementation.

This guide helps readers of any level find a relevant subject. The domain folders are being developed; their locations show the intended structure, not a guarantee that every lesson is ready.

## Choose a domain from your question

Start with what you need to explain. “The deployment failed” may lead to delivery, identity, networking, or the application runtime. “The server is slow” may involve processes, memory, storage, network dependencies, or workload behavior.

A domain gives you a lens for investigation or learning. It does not establish the cause of a problem. Use observations to decide which lens is relevant.

## Foundations

| Domain | What to understand |
| --- | --- |
| [Operating systems and compute](../03-technical-domains/01-operating-systems-compute/) | Processes, services, resources, and host behavior |
| [Computer architecture and hardware](../03-technical-domains/02-computer-architecture-hardware/) | Hardware resources and their effects on software execution |
| [Networking](../03-technical-domains/03-networking/) | Connectivity, addressing, protocols, and traffic paths |
| [Programming and scripting](../03-technical-domains/04-programming-scripting/) | Expressing logic and automating repeatable work |
| [Data formats and configuration](../03-technical-domains/05-data-formats-configuration/) | Representing data and interpreting configuration correctly |
| [Version control](../03-technical-domains/06-version-control/) | Recording, reviewing, and coordinating changes |

These domains support many later subjects. You do not need to master every detail before proceeding, but you should be able to identify and address the prerequisites a guide assumes.

## Delivery and environment management

| Domain | What to understand |
| --- | --- |
| [Build engineering](../03-technical-domains/07-build-engineering/) | Turning source and dependencies into usable outputs |
| [CI/CD](../03-technical-domains/08-cicd/) | Integration, verification, and delivery of changes |
| [Release engineering](../03-technical-domains/09-release-engineering/) | Coordinating releases, promotion, and recovery |
| [Artifacts and packages](../03-technical-domains/10-artifacts-packages/) | Distribution, identity, dependencies, and provenance |
| [Infrastructure as code](../03-technical-domains/11-infrastructure-as-code/) | Describing infrastructure and managing its changes |
| [Configuration management](../03-technical-domains/12-configuration-management/) | Maintaining intended system configuration |
| [Image building and provisioning](../03-technical-domains/13-image-building-provisioning/) | Preparing and supplying operating environments |
| [Virtualization](../03-technical-domains/14-virtualization/) | Managing virtualized compute and its boundaries |
| [Containers](../03-technical-domains/15-containers/) | Packaging and running processes with defined isolation |
| [Kubernetes](../03-technical-domains/16-kubernetes/) | Coordinating containerized workloads and supporting resources |
| [GitOps](../03-technical-domains/17-gitops/) | Using versioned desired state and reconciliation workflows |
| [Cloud computing](../03-technical-domains/18-cloud-computing/) | Service models, infrastructure responsibilities, and cloud operations |
| [Serverless and PaaS](../03-technical-domains/19-serverless-paas/) | Managed execution and platform service tradeoffs |

PaaS means platform as a service. Managed services change responsibility boundaries; they do not remove the need to understand application behavior, identity, dependencies, and cost.

## Operating reliable systems

| Domain | What to understand |
| --- | --- |
| [Observability](../03-technical-domains/20-observability/) | Gathering and interpreting evidence of system behavior |
| [SRE and reliability](../03-technical-domains/21-sre-reliability/) | Service objectives, failure handling, and operational engineering |
| [Incident management](../03-technical-domains/22-incident-management/) | Coordinating response, communication, and recovery |
| [Production debugging](../03-technical-domains/23-production-debugging/) | Testing hypotheses using relevant evidence |
| [Distributed systems](../03-technical-domains/24-distributed-systems/) | Coordination, partial failure, and consistency tradeoffs |
| [Databases](../03-technical-domains/25-databases/) | Data access, correctness, operation, and recovery |
| [Messaging and streaming](../03-technical-domains/26-messaging-streaming/) | Communication through events and messages |
| [Storage](../03-technical-domains/27-storage/) | Persistence, access, capacity, and performance |
| [Backup and disaster recovery](../03-technical-domains/28-backup-disaster-recovery/) | Recoverability and evidence from restore testing |

## Security, platforms, and service boundaries

| Domain | What to understand |
| --- | --- |
| [Security](../03-technical-domains/29-security/) | Risks, protective controls, detection, and response |
| [Policy and governance](../03-technical-domains/30-policy-governance/) | Rules, ownership, and evidence for controlled operation |
| [Platform engineering](../03-technical-domains/31-platform-engineering/) | Reusable capabilities for engineering teams |
| [Developer infrastructure](../03-technical-domains/32-developer-infrastructure/) | Systems that support development work |
| [Service mesh networking](../03-technical-domains/33-service-mesh-networking/) | Communication controls and operational boundaries between services |
| [API infrastructure](../03-technical-domains/34-api-infrastructure/) | Interfaces, traffic handling, and service access |
| [Edge, CDN, and DNS](../03-technical-domains/35-edge-cdn-dns/) | Name resolution and traffic delivery near users |
| [FinOps](../03-technical-domains/36-finops/) | Connecting technology usage, cost, and organizational decisions |

API means application programming interface; CDN means content delivery network; DNS means Domain Name System. Domain guides should explain these subjects in depth rather than assuming that an acronym is sufficient understanding.

## Engineering effectiveness and specialist infrastructure

| Domain | What to understand |
| --- | --- |
| [Testing](../03-technical-domains/37-testing/) | Evidence that behavior meets defined expectations |
| [Performance](../03-technical-domains/38-performance/) | Workload behavior, constraints, and measurement |
| [Terminal productivity](../03-technical-domains/39-terminal-productivity/) | Effective work in command-line environments |
| [Documentation and knowledge](../03-technical-domains/40-documentation-knowledge/) | Maintaining usable engineering information |
| [Architecture and system design](../03-technical-domains/41-architecture-system-design/) | Decisions shaped by requirements and constraints |
| [Datacenter and bare metal](../03-technical-domains/42-datacenter-bare-metal/) | Physical infrastructure and its operating responsibilities |
| [IT service management](../03-technical-domains/43-itsm/) | Service ownership, change, and operational coordination |
| [MLOps](../03-technical-domains/44-mlops/) | Engineering and operations around machine-learning systems |
| [AI and GPU infrastructure](../03-technical-domains/45-ai-gpu-infrastructure/) | Infrastructure for AI workloads and accelerator use |
| [AIOps](../03-technical-domains/46-aiops/) | Applying AI-assisted approaches to operational tasks |
| [HPC](../03-technical-domains/47-hpc/) | Infrastructure and execution for high-performance computing |

GPU means graphics processing unit. Specialist compute subjects require explicit hardware and software context in practical material. A local simulation cannot establish every behavior of an accelerator or a large computing environment.

## Use a domain folder well

Read the README for scope, then use the curriculum to identify progression. Documentation and standards files provide deeper references. Tool categories help you connect concepts to implementations. Production problem material shows where the knowledge matters under failure. Related domains explain useful dependencies.

**Illustrative example:** to understand why an application cannot reach a database, begin with networking and the relevant application context. Explore database material for connection and service behavior, and security material for access constraints. Use the [production problem guide](solve-a-production-problem.md) to distinguish possible causes through evidence.

## Make learning measurable

Choose one outcome: explain a request path, interpret a process state, describe a release boundary, or demonstrate a restore in a controlled exercise. Record prerequisites and evidence. Move to a tool or provider only when you can explain what capability you need.

Continue with [Find a tool](find-a-tool.md), [Browse by cloud](browse-by-cloud.md), or [Choose your career](choose-your-career.md).

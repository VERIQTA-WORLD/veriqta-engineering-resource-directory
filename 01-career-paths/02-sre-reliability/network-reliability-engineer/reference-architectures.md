# Network reliability engineer: reference architectures and design guidance

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these designs, patterns, and engineering accounts to test assumptions and compare alternatives. Provider blueprints, project guides, community principles, and formal specifications have different scopes.

## Browse this page

- [Traffic steering and isolation](#traffic-steering-and-isolation)
- [Provider and workload network designs](#provider-and-workload-network-designs)
- [Network-dependent application behavior](#network-dependent-application-behavior)

## Traffic steering and isolation

Compare service and global traffic-distribution concepts with the actual failure-domain and state assumptions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Load balancing at the frontend](https://sre.google/sre-book/load-balancing-frontend/) | Explore traffic distribution and frontend reliability across infrastructure boundaries. | Advanced; public chapter. Provider and network topology determine which mechanisms are available. |
| [Load balancing in the datacenter](https://sre.google/sre-book/load-balancing-datacenter/) | Compare service load-balancing behavior, health signals, and backend selection. | Advanced; public chapter. A healthy endpoint may still be unable to satisfy the requested operation. |
| [Azure health endpoint monitoring pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/health-endpoint-monitoring) | Design health interfaces that distinguish service capability from simple process existence. | Intermediate; public pattern. Deep health checks can create dependency load and correlated failure. |
| [Azure bulkhead pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead) | Explore resource isolation between workloads and dependency paths. | Intermediate; public pattern. Isolation adds capacity and routing decisions; test the boundaries actually enforced. |
| [Azure deployment stamps pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/deployment-stamp) | Compare independently deployable workload units and their failure boundaries. | Advanced; public pattern. Routing, data ownership, and stamp-level capacity affect recovery and operational complexity. |
| [Cloud design patterns](https://learn.microsoft.com/en-us/azure/architecture/patterns/) | Compare patterns addressing distributed-system concerns and trade-offs. | Intermediate; examples are provider-oriented, while many problem statements apply more broadly. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |

## Provider and workload network designs

Choose designs matching the deployed cloud, routing responsibility, and workload model. Review their failure and cost assumptions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS networking architecture guidance](https://aws.amazon.com/architecture/networking-content-delivery/) | Find provider architecture references for network connectivity and traffic delivery. | Intermediate; public discovery collection. Review a selected design separately; service charges and regional constraints vary. |
| [Azure networking documentation](https://learn.microsoft.com/en-us/azure/networking/) | Find provider-specific connectivity, routing, DNS, and network operating references. | Intermediate; public documentation collection. Select the service used by the workload; diagrams do not prove effective routing or policy. |
| [Google Cloud VPC documentation](https://cloud.google.com/vpc/docs) | Review virtual-network, routing, firewall, and connectivity behavior. | Intermediate; public provider reference. Default and effective policies must be inspected in the actual project. |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Intermediate to advanced; filter by your workload and operational constraints. |
| [Amazon EKS best practices](https://docs.aws.amazon.com/eks/latest/best-practices/introduction.html) | Review Kubernetes workload and cluster-design guidance for EKS. | Advanced; EKS-specific assumptions must be separated from general Kubernetes advice. |
| [AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks) | Examine a documented infrastructure baseline for an Azure Kubernetes Service cluster. | Advanced; adapt identity, network, availability, and cost choices to requirements. |

## Network-dependent application behavior

Treat DNS, connection retries, timeouts, and load balancing as application dependencies too. Document observations and alternatives in a decision record.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [Azure circuit breaker pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker) | Compare dependency-failure containment and recovery-probe behavior. | Intermediate; public pattern. Thresholds and reset behavior must match the dependency and user impact. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [C4 model](https://c4model.com/) | Describe software systems at useful levels of architectural abstraction. | Foundation onward; diagrams communicate structure but do not establish operational correctness. |
| [Architecture Decision Records](https://adr.github.io/) | Find guidance and resources for recording architectural decisions. | Foundation onward; keep decisions connected to evidence and later changes. |
| [SLO engineering case studies](https://sre.google/workbook/slo-engineering-case-studies/) | Compare service-objective decisions and measurement approaches in concrete cases. | Intermediate; public chapter. Keep the service boundary and user expectations explicit. |

[Browse the other collections](README.md#resource-collections)

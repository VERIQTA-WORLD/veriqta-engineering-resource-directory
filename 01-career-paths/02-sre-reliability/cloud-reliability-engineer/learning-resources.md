# Cloud reliability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Reliability and cloud design](#reliability-and-cloud-design)
- [Implementation tutorials and recovery concepts](#implementation-tutorials-and-recovery-concepts)
- [Historical provider and dependency incidents](#historical-provider-and-dependency-incidents)
- [Foundation-level SRE training](#foundation-level-sre-training)

## Reliability and cloud design

Use service-objective and design references together; availability, data loss, restoration time, and cost are different decisions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html) | Explore security and reliability together in system design and operations. | Advanced; openly readable. Examples require interpretation for your environment. |
| [AWS Well-Architected reliability pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | Review reliability questions for cloud workload foundations, change, and recovery. | Intermediate; public provider framework. Review actual service limits and workload evidence; framework use is not certification. |
| [Azure Well-Architected reliability guidance](https://learn.microsoft.com/en-us/azure/well-architected/reliability/) | Find provider guidance for failure analysis, redundancy, recovery, and reliability review. | Intermediate; public framework. Apply to the deployed services and their documented responsibility boundaries. |
| [Google Cloud reliability framework](https://cloud.google.com/architecture/framework/reliability) | Review workload reliability principles and provider-specific design considerations. | Intermediate; public framework. Architecture guidance does not guarantee that every managed service meets your objective. |

## Implementation tutorials and recovery concepts

Choose topic material for the provider and technology operated. Learning catalogs require separate review of the selected tutorial or course.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [HashiCorp tutorials](https://developer.hashicorp.com/tutorials) | Find product-maintained tutorials for infrastructure, images, secrets, and related workflows. | Foundation to advanced; tutorial dependencies and cloud charges vary. |
| [Pulumi tutorials](https://www.pulumi.com/tutorials/) | Find infrastructure learning examples organized around supported tools and platforms. | Intermediate; review account, language, and cloud requirements before starting. |
| [Kubernetes tutorials](https://kubernetes.io/docs/tutorials/) | Study official walkthroughs for workloads, services, configuration, and clusters. | Foundation to intermediate; use the version and environment expected by the tutorial. |
| [Google SRE Workbook: managing load](https://sre.google/workbook/managing-load/) | Connect load balancing, overload management, and failure handling to service behavior. | Intermediate; public chapter. Adapt the examples to local traffic, dependencies, and recovery constraints. |
| [Non-abstract large system design](https://sre.google/workbook/non-abstract-design/) | Connect system design to concrete capacity, dependency, and failure assumptions. | Advanced; public workbook chapter. Recalculate workload assumptions rather than reusing example capacity figures. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |

## Historical provider and dependency incidents

Read original accounts to examine mechanisms and recovery constraints. Historical reports do not establish a current provider guarantee.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS S3 service disruption summary, 2017](https://aws.amazon.com/message/41926/) | Read the provider's original account of a historical regional service disruption. | Intermediate; public historical report. Its documented scope and corrective actions are specific to that event. |
| [Cloudflare control-plane and analytics outage](https://blog.cloudflare.com/post-mortem-on-cloudflare-control-plane-and-analytics-outage/) | Compare dependency, datacenter, and recovery concerns in an original outage account. | Advanced; public historical postmortem. Distinguish affected control-plane and analytics functions from unaffected services. |
| [GitHub October 2018 incident analysis](https://github.blog/news-insights/company-news/oct21-post-incident-analysis/) | Read the original incident analysis of database topology and recovery decisions. | Advanced; public historical report. Findings describe that incident and architecture, not a current service guarantee. |
| [GitLab database incident postmortem](https://about.gitlab.com/blog/gitlab-dot-com-database-incident/) | Study operational mistakes, recovery dependencies, and backup-validation lessons in an original report. | Intermediate; public historical incident account. Do not confuse configured backup procedures with demonstrated restore capability. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |
| [CNCF Slack community](https://slack.cncf.io/) | Find project and community discussion channels. | All levels; account and community-guideline acceptance required. Community support has no guaranteed service level. |

## Foundation-level SRE training

Use this direct beginner module to understand the operating practice and human responsibilities before turning to advanced implementation references. It is a topic option, not a required curriculum.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Microsoft Learn: introduction to SRE](https://learn.microsoft.com/en-us/training/modules/intro-to-site-reliability-engineering/) | Browse a beginner module explaining SRE context, principles, human responsibilities, and getting started. | Foundation; publicly readable training module with no stated prerequisites. Sign-in is required for profile-linked assessment results; it is introductory guidance, not a production implementation lab. |

[Browse the other collections](README.md#resource-collections)

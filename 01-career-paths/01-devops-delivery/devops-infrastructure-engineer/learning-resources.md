# DevOps infrastructure engineer: learning resources

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Hosts and infrastructure implementation

These resources support configuration, image creation, and provisioning skills. Match examples to the actual distribution, provider, and installed tooling.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Debian Administrator's Handbook](https://www.debian.org/doc/manuals/debian-handbook/) | Study host administration, packages, networking, security, and service configuration together. | Foundation to intermediate; public handbook. The retrieved edition covers Debian Bullseye; verify commands and package arrangements against the system you operate. |
| [GNU Bash manual](https://www.gnu.org/software/bash/manual/bash.html) | Check expansion, quoting, pipelines, redirection, and exit behavior when reviewing shell scripts. | Foundation to advanced; publicly readable GNU Bash reference. Other shells have different behavior. Source retrieval was blocked during this review; availability and the current document remain pending verification. |
| [Python tutorial](https://docs.python.org/3/tutorial/) | Read the language tutorial before maintaining automation that parses data, calls services, or manages files. | Foundation in Python; assumes basic programming knowledge. Publicly readable; use an isolated virtual environment and match the installed interpreter. |
| [Ansible example playbooks](https://github.com/ansible/ansible-examples) | Inspect project-maintained examples of application configuration and orchestration. | Intermediate; public example repository. Check age, target assumptions, and credentials; adapt in disposable systems rather than treating examples as production defaults. |
| [HashiCorp tutorials](https://developer.hashicorp.com/tutorials) | Find product-maintained tutorials for infrastructure, images, secrets, and related workflows. | Public reference. Foundation to advanced; tutorial dependencies and cloud charges vary. |
| [Packer tutorials](https://developer.hashicorp.com/packer/tutorials) | Find image-building walkthroughs and provider-specific examples. | Intermediate; public tutorial collection. Image builds require supported builders, credentials, compute, and removal of retained images. |
| [Pulumi tutorials](https://www.pulumi.com/tutorials/) | Find infrastructure learning examples organized around supported tools and platforms. | Public reference. Intermediate; review account, language, and cloud requirements before starting. |

## Containers and infrastructure operations

Combine application-facing Kubernetes learning with references for cluster, node, and storage operation. Course catalogs need separate course-level evaluation.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes tutorials](https://kubernetes.io/docs/tutorials/) | Study official walkthroughs for workloads, services, configuration, and clusters. | Public reference. Foundation to intermediate; use the version and environment expected by the tutorial. |
| [Introduction to DevOps and SRE (LFS162)](https://training.linuxfoundation.org/training/introduction-to-devops-and-site-reliability-engineering-lfs162/) | Explore an introductory course connecting delivery, infrastructure automation, observability, and reliability. | Public reference. Foundational DevOps content; assumes Linux, networking, scripting, security, and troubleshooting knowledge. Enrollment conditions apply. |
| [Linux Foundation training catalog](https://training.linuxfoundation.org/full-catalog/) | Discover courses and certifications related to Linux, Kubernetes, cloud-native, and security topics. | Public reference. Foundation to advanced; access varies by offering. Certification is optional and does not prove architecture competence. |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Public reference. Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Public reference. Intermediate to advanced; openly readable. Requires familiarity with service operation. |

## Security, reliability, and economics

Use these to connect implementation choices to credentials, failure behavior, toil, and ongoing spend.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html) | Explore security and reliability together in system design and operations. | Public reference. Advanced; openly readable. Examples require interpretation for your environment. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Public reference. Advanced; validate containment strategies with bounded tests and measurements. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize cost accountability, allocation, forecasting, and optimization work. | Public reference. Intermediate; a practice framework, not a tool or a guarantee of savings. |
| [DORA capabilities](https://dora.dev/capabilities/) | Find research-informed delivery and organizational capability references. | Public reference. Intermediate; assess evidence and local constraints before prioritizing changes. |

## Architecture and project discovery

These collections help locate project documentation and provider examples. A catalog entry is not a compatibility check for the environment.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Architecture Center](https://aws.amazon.com/architecture/) | Discover architecture guidance and reference material by workload and concern. | Public reference. Intermediate to advanced; evaluate publication scope and required AWS services. |
| [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/) | Compare reference architectures, patterns, and decision guidance. | Public reference. Intermediate to advanced; implementation choices and estimates require workload-specific validation. |
| [Google Cloud Architecture Center](https://cloud.google.com/architecture) | Find architecture guides and implementation references for Google Cloud. | Public reference. Intermediate to advanced; filter by your workload and operational constraints. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Public reference. Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |
| [CNCF Cloud Native Landscape](https://landscape.cncf.io/) | Discover technologies across cloud-native categories and ecosystems. | Public reference. Intermediate; directory inclusion is not endorsement or a recommendation to adopt. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

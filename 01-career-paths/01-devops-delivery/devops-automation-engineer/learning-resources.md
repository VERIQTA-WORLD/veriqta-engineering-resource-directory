# DevOps automation engineer: learning resources

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Scripting and tests

These resources support implementation skills, without prescribing one language for every team. Work through examples using throwaway files and test targets.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Python tutorial](https://docs.python.org/3/tutorial/) | Read the language tutorial before maintaining automation that parses data, calls services, or manages files. | Foundation in Python; assumes basic programming knowledge. Publicly readable; use an isolated virtual environment and match the installed interpreter. |
| [GNU Bash manual](https://www.gnu.org/software/bash/manual/bash.html) | Check expansion, quoting, pipelines, redirection, and exit behavior when reviewing shell scripts. | Foundation to advanced; publicly readable GNU Bash reference. Other shells have different behavior. Source retrieval was blocked during this review; availability and the current document remain pending verification. |
| [PowerShell documentation](https://learn.microsoft.com/en-us/powershell/) | Find language, scripting, remoting, and administration references for PowerShell automation. | Foundation onward; publicly readable. Distinguish PowerShell releases and Windows PowerShell; platform availability varies by module. |
| [Pro Git](https://git-scm.com/book/en/v2) | Strengthen understanding of Git behavior, collaboration, and repository workflows. | Public reference. Foundation to intermediate; openly readable. Practice with disposable repositories. |
| [pytest](https://docs.pytest.org/en/stable/) | Test Python automation with fixtures, assertions, parametrization, and temporary environments. | Intermediate; public project documentation. Mocks cannot establish that a live provider behaves correctly. |
| [Pester documentation](https://pester.dev/docs/quick-start) | Write and run tests for PowerShell code using the project's introductory documentation. | Intermediate; public guide. Tests that call real systems need disposable targets and explicit cleanup. |
| [Bats-core](https://bats-core.readthedocs.io/en/stable/) | Write repeatable shell tests around observable outputs and exit statuses. | Intermediate; public project documentation. Tests need disposable fixtures when scripts alter systems. |
| [Requests](https://requests.readthedocs.io/en/latest/) | Implement Python HTTP clients using documented sessions, authentication, and request interfaces. | Intermediate; public documentation. Set explicit timeouts and handle response semantics; do not log tokens. |

## Infrastructure and configuration practice

Choose tutorials matching your provider, language, and execution environment. Read the cost and cleanup instructions before provisioning.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [HashiCorp tutorials](https://developer.hashicorp.com/tutorials) | Find product-maintained tutorials for infrastructure, images, secrets, and related workflows. | Public reference. Foundation to advanced; tutorial dependencies and cloud charges vary. |
| [Pulumi tutorials](https://www.pulumi.com/tutorials/) | Find infrastructure learning examples organized around supported tools and platforms. | Public reference. Intermediate; review account, language, and cloud requirements before starting. |
| [Packer tutorials](https://developer.hashicorp.com/packer/tutorials) | Find image-building walkthroughs and provider-specific examples. | Intermediate; public tutorial collection. Image builds require supported builders, credentials, compute, and removal of retained images. |
| [Ansible example playbooks](https://github.com/ansible/ansible-examples) | Inspect project-maintained examples of application configuration and orchestration. | Intermediate; public example repository. Check age, target assumptions, and credentials; adapt in disposable systems rather than treating examples as production defaults. |
| [Terraform testing tutorial](https://developer.hashicorp.com/terraform/tutorials/configuration-language/test) | Practice assertions and test setup for infrastructure configuration. | Intermediate; public tutorial. Tests may provision infrastructure; inspect run modes, permissions, and teardown before execution. |

## Automation as an operational improvement

Use these to connect implementation work to reduced toil and safer delivery. Publishing a script is not the same as changing an unreliable workflow.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [The evolution of automation](https://sre.google/sre-book/automation-at-google/) | Study how automation changes operating practices and control boundaries. | Intermediate; public book chapter. Large-scale examples are design references, not a requirement to build an equivalent platform. |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Public reference. Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Public reference. Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Continuous Delivery book resources](https://continuousdelivery.com/) | Explore the authors' delivery principles and book-related material. | Intermediate; website resources and the commercially distributed book are distinct. |
| [DORA capabilities](https://dora.dev/capabilities/) | Find research-informed delivery and organizational capability references. | Public reference. Intermediate; assess evidence and local constraints before prioritizing changes. |

## Security and wider discovery

Security engineering and project communities provide context for trust boundaries and integration choices. Catalogs and talks are discovery sources, not individually reviewed courses.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Building Secure and Reliable Systems](https://google.github.io/building-secure-and-reliable-systems/raw/toc.html) | Explore security and reliability together in system design and operations. | Public reference. Advanced; openly readable. Examples require interpretation for your environment. |
| [NIST Secure Software Development Framework, SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final) | Review secure development practices and their organizational integration. | Public reference. Intermediate to advanced; use the publication's stated scope and any applicable local requirements. |
| [Introduction to DevOps and SRE (LFS162)](https://training.linuxfoundation.org/training/introduction-to-devops-and-site-reliability-engineering-lfs162/) | Explore an introductory course connecting delivery, infrastructure automation, observability, and reliability. | Public reference. Foundational DevOps content; assumes Linux, networking, scripting, security, and troubleshooting knowledge. Enrollment conditions apply. |
| [CNCF video channel](https://www.youtube.com/@cncf) | Discover project talks, conference sessions, and cloud-native engineering discussions. | Public reference. Intermediate to advanced; speaker claims and older sessions need checking against current documentation. |
| [Continuous Delivery Foundation](https://cd.foundation/) | Discover delivery projects, events, and community material. | Public reference. Intermediate; follow project links to their own documentation and maintenance information. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

# Infrastructure reliability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Host and resource foundations](#host-and-resource-foundations)
- [Infrastructure implementation and tests](#infrastructure-implementation-and-tests)
- [Reliability and recovery reasoning](#reliability-and-recovery-reasoning)

## Host and resource foundations

These sources connect system behavior to diagnostic evidence. Match version-specific details to the installed estate.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Debian Administrator's Handbook](https://www.debian.org/doc/manuals/debian-handbook/) | Study host administration, packages, networking, security, and service configuration together. | Foundation to intermediate; public handbook. The retrieved edition covers Debian Bullseye; verify commands and package arrangements against the system you operate. |
| [The USE method](https://www.brendangregg.com/usemethod.html) | Organize resource analysis around utilization, saturation, and errors. | Intermediate; public author reference. High utilization alone does not establish the limiting resource. |
| [Brendan Gregg: systems performance](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) | Find the author's description and supporting material for a systems-performance reference. | Intermediate to advanced; public book page. The book itself is a separate purchase; review edition-specific tools. |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |
| [cloud-init documentation](https://cloudinit.readthedocs.io/en/latest/) | Compare first-boot provisioning, datasource handling, and machine initialization workflows. | Intermediate; public documentation. Instance metadata, credentials, and repeated initialization require careful review. |
| [systemd project documentation](https://systemd.io/) | Find project-maintained explanations, administrator references, interfaces, and navigation to the manual pages. | Intermediate; public discovery page. Review the selected manual separately and match features to the distribution's installed systemd version. |

## Infrastructure implementation and tests

Choose the provider and configuration examples you actually operate; test interfaces and interrupted-run behavior before fleet-wide use.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [HashiCorp tutorials](https://developer.hashicorp.com/tutorials) | Find product-maintained tutorials for infrastructure, images, secrets, and related workflows. | Foundation to advanced; tutorial dependencies and cloud charges vary. |
| [Pulumi tutorials](https://www.pulumi.com/tutorials/) | Find infrastructure learning examples organized around supported tools and platforms. | Intermediate; review account, language, and cloud requirements before starting. |
| [Packer tutorials](https://developer.hashicorp.com/packer/tutorials) | Find image-building walkthroughs and provider-specific examples. | Intermediate; public tutorial collection. Image builds require supported builders, credentials, compute, and removal of retained images. |
| [Ansible example playbooks](https://github.com/ansible/ansible-examples) | Inspect project-maintained examples of application configuration and orchestration. | Intermediate; public example repository. Check age, target assumptions, and credentials; adapt in disposable systems rather than treating examples as production defaults. |
| [Terraform testing tutorial](https://developer.hashicorp.com/terraform/tutorials/configuration-language/test) | Practice assertions and test setup for infrastructure configuration. | Intermediate; public tutorial. Tests may provision infrastructure; inspect run modes, permissions, and teardown before execution. |

## Reliability and recovery reasoning

Study overload, consensus, integrity, and operating work together rather than equate reliability with redundant machines.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [GitLab database incident postmortem](https://about.gitlab.com/blog/gitlab-dot-com-database-incident/) | Study operational mistakes, recovery dependencies, and backup-validation lessons in an original report. | Intermediate; public historical incident account. Do not confuse configured backup procedures with demonstrated restore capability. |

[Browse the other collections](README.md#resource-collections)

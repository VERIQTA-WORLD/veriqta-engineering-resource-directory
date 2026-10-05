# DevOps automation engineer

This collection focuses on the code and workflows that automate delivery and operations: scripts, infrastructure changes, configuration, API integrations, tests, and recovery paths. The central question is whether an operation is repeatable, observable, appropriately authorized, and recoverable when only part of it succeeds.

Use the scripting references for implementation, the test resources for confidence, and the operational references for failure handling. Cloud, container, and platform material is included where automation crosses those systems; it is not an instruction to adopt every platform.

[DevOps delivery careers](../README.md) · [All career categories](../../README.md)

## Browse the collection

| Collection | What you will find |
| --- | --- |
| [Toolkit](toolkit.md) | Tools grouped by implementation or operating task, with alternatives and selection notes. |
| [Official documentation](official-documentation.md) | Authoritative manuals, API references, and focused operating guides. |
| [Reference architectures](reference-architectures.md) | Documented designs, patterns, assumptions, and decision resources. |
| [Learning resources](learning-resources.md) | Books, tutorials, research, talks, and discovery collections by topic. |
| [Labs and projects](labs-and-projects.md) | Practice environments, examples, workshops, and implementation repositories. |
| [Production responsibilities](production-responsibilities.md) | Operating concerns connected to diagnostic, incident, and recovery resources. |
| [Standards and frameworks](standards-and-frameworks.md) | Specifications, security guidance, and review frameworks with scope distinctions. |
| [Related careers](related-careers.md) | Adjacent collections, their overlap, and their development status. |

## Useful entry points

Choose the reference that matches your immediate task. These links are starting points into the wider collections, not a required sequence.

| Resource | When to open it | Level and access |
| --- | --- | --- |
| [Python tutorial](https://docs.python.org/3/tutorial/) | Read the language tutorial before maintaining automation that parses data, calls services, or manages files. | Foundation in Python; assumes basic programming knowledge. Publicly readable; use an isolated virtual environment and match the installed interpreter. |
| [GNU Bash manual](https://www.gnu.org/software/bash/manual/bash.html) | Check expansion, quoting, pipelines, redirection, and exit behavior when reviewing shell scripts. | Foundation to advanced; publicly readable GNU Bash reference. Other shells have different behavior. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Terraform testing](https://developer.hashicorp.com/terraform/language/tests) | Review native test structures for modules and infrastructure workflows. | Intermediate; some test arrangements create resources. Read execution and cleanup behavior first. |
| [GitHub reusable workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) | Define shared workflow interfaces, inputs, secrets, and calls between repositories. | Intermediate; public documentation. Review secret propagation, environment behavior, permissions, and version pinning. |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |

## Coverage and practical use

shell and Python correctness; API contracts, authentication, pagination, timeouts and retry behavior; idempotency and partial failure; infrastructure and configuration testing; reusable delivery workflows and artifact flow; identity, secrets and policy; execution evidence, ownership, rollback and cleanup.

Continuous integration and continuous delivery (CI/CD) describe connected delivery practices. Infrastructure as code (IaC) describes infrastructure managed through versioned configuration or code. GitOps resources address desired-state delivery and reconciliation. Use each approach only where its responsibilities and failure behavior are understood.

Official external destinations are used while the repository catalog is being established. Software, hosted-service, and cloud charges must be assessed separately from public access to a reference. Source review does not certify a deployment, a full course, or an entire book.

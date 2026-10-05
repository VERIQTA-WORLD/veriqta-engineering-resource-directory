# DevOps automation engineer: production responsibilities and operational resources

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Make failures explicit

Define retries, stopping conditions, and partial-success evidence before a workflow is operated. Investigate failed targets rather than suppressing errors to obtain a green run.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Ansible execution strategies](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_strategies.html) | Select batching, parallelism, and task ordering for a fleet change. | Intermediate; publicly readable. More parallel execution can increase blast radius and load on shared services. |
| [Python subprocess reference](https://docs.python.org/3/library/subprocess.html) | Handle command execution, arguments, exit codes, streams, and timeouts in Python automation. | Intermediate; publicly readable API reference. Shell execution and untrusted input need explicit security review. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Public reference. Advanced; operation semantics determine which retry behavior is safe. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Public reference. Advanced; official PDF. Values require latency and failure evidence from your own system. |

## Control changes and shared state

Capture reviewed changes, execution identity, and the state backend involved. Investigate competing runs and stale state before applying corrective operations.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Public reference. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform import](https://developer.hashicorp.com/terraform/language/import) | Bring existing infrastructure into configuration while checking ownership and planned changes. | Intermediate; public reference. Import does not by itself reconstruct an accurate configuration or remove drift. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review runner trust, workflow access, and delivery credential exposure. | Intermediate; public contributions and privileged jobs need distinct trust treatment. |
| [GitHub Actions OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect) | Evaluate identity federation between workflows and external providers. | Advanced; public conceptual guide. Trust policy must bind the intended repository and execution context, not merely the identity provider. |

## Protect credentials and evidence

Logs, plans, inventories, and artifacts may contain secrets. Define what is retained, who can retrieve it, and which mechanism redacts sensitive data.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Python logging reference](https://docs.python.org/3/library/logging.html) | Build structured execution evidence and separate diagnostic messages from automation results. | Intermediate; publicly readable. Redact credentials and sensitive parameters before recording them. |
| [Ansible Vault](https://docs.ansible.com/ansible/latest/vault_guide/index.html) | Review encrypted-data handling in configuration automation. | Public reference. Intermediate; encryption at rest does not prevent exposure after decryption. |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Public reference. Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [SOPS](https://github.com/getsops/sops) | Review encrypted configuration-file workflows with supported key services. | Public reference. Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak. |
| [GitHub workflow artifacts](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflow-artifacts) | Understand how outputs move between jobs and remain available after workflow execution. | Foundation onward; public documentation. Retention, access, and storage limits depend on service settings and account terms. |
| [SLSA specification](https://slsa.dev/spec/) | Review supply-chain assurance requirements and provenance concepts. | Public reference. Advanced; select the relevant published specification. Do not confuse a working draft with a stable requirement. |

## Operate and retire automation

Give every workflow an owner, supported environment, diagnostic path, and recovery procedure. Track reduced effort and failure frequency rather than only counting successful executions.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Eliminating toil](https://sre.google/sre-book/eliminating-toil/) | Distinguish repeated operational work from engineering improvements when selecting automation. | Foundation onward; public book chapter. The examples describe Google's context; measure local effort and risk before transferring targets. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Public reference. Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Public reference. Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Jenkins backup and restore](https://www.jenkins.io/doc/book/system-administration/backing-up/) | Plan recovery of controller configuration and data rather than only rebuilding agents. | Intermediate; public operating guide. Protect backed-up secrets and exercise restore in an isolated environment. |
| [GitLab database outage report, January 2017](https://about.gitlab.com/blog/2017/02/01/gitlab-dot-com-database-incident/) | Study an original recovery incident and the importance of tested backup procedures. | Public reference. Advanced; historical incident. Distinguish recorded facts from assumptions about present systems. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Public reference. Intermediate; cost work requires billing and usage data, not estimates alone. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Standards and frameworks](standards-and-frameworks.md)

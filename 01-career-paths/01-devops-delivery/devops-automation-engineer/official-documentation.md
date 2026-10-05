# DevOps automation engineer: official documentation

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Process execution and API integration

Refer to exact API semantics when a script invokes commands or remote services. A nonzero exit, HTTP error, and timeout should not all be treated as the same failure.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Python subprocess reference](https://docs.python.org/3/library/subprocess.html) | Handle command execution, arguments, exit codes, streams, and timeouts in Python automation. | Intermediate; publicly readable API reference. Shell execution and untrusted input need explicit security review. |
| [Python logging reference](https://docs.python.org/3/library/logging.html) | Build structured execution evidence and separate diagnostic messages from automation results. | Intermediate; publicly readable. Redact credentials and sensitive parameters before recording them. |
| [Python virtual environments](https://docs.python.org/3/library/venv.html) | Separate automation dependencies from the host interpreter and reproduce a tool's execution environment. | Foundation; publicly readable. A virtual environment isolates packages, not operating-system privileges or network access. |
| [Requests](https://requests.readthedocs.io/en/latest/) | Implement Python HTTP clients using documented sessions, authentication, and request interfaces. | Intermediate; public documentation. Set explicit timeouts and handle response semantics; do not log tokens. |
| [GitHub REST API documentation](https://docs.github.com/en/rest) | Integrate repository and delivery operations through documented API endpoints. | Intermediate; public API reference. Authentication, pagination, permissions, and rate limits must be handled by the client. |
| [GitHub REST API best practices](https://docs.github.com/en/rest/using-the-rest-api/best-practices-for-using-the-rest-api) | Review authenticated requests, pagination, rate limits, and failure handling for repository integrations. | Intermediate; public operational reference. Follow provider guidance and response headers rather than hard-coding retry intervals for every failure. |
| [PowerShell error-handling reference](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_try_catch_finally) | Review try, catch, and finally behavior when implementing operational recovery paths. | Intermediate; public reference. Understand terminating and non-terminating errors; a catch block does not make all failures equivalent. |
| [GNU Bash manual](https://www.gnu.org/software/bash/manual/bash.html) | Check expansion, quoting, pipelines, redirection, and exit behavior when reviewing shell scripts. | Foundation to advanced; publicly readable GNU Bash reference. Other shells have different behavior. Source retrieval was blocked during this review; availability and the current document remain pending verification. |
| [jq manual](https://jqlang.org/manual/) | Inspect and transform JSON returned by command-line clients and infrastructure APIs. | Foundation onward; publicly readable manual. Validate missing fields rather than assuming one provider response shape. |
| [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) | Review machine-readable API contracts and compare documented requests, schemas, and responses. | Intermediate; public specification. The latest document may differ from the version supported by a chosen validator or client generator. |
| [JSON Schema documentation](https://json-schema.org/learn/) | Find schema concepts and validation references for structured automation inputs and outputs. | Intermediate; public learning and reference collection. Choose a supported dialect; schema validation cannot prove operational intent or authorization. |

## Configuration convergence and controlled targeting

Review change detection, errors, inventory, and batching before promoting a playbook beyond a disposable environment.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Ansible inventory guide](https://docs.ansible.com/projects/ansible/latest/inventory_guide/intro_inventory.html) | Organize hosts, groups, variables, and inventory sources for controlled targeting. | Intermediate; public reference. Protect inventory data and test precedence before widening the target group. |
| [Ansible error handling](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_error_handling.html) | Define failures, changed results, handler behavior, and stopping conditions for multi-host execution. | Intermediate; publicly readable reference. Ignoring an error can conceal incomplete configuration; unreachable hosts need separate handling. |
| [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html) | Review simulated changes and configuration differences before a deployment. | Intermediate; public reference. Module support varies, explicit task settings can allow changes, and diff output may expose secrets. |
| [Ansible execution strategies](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_strategies.html) | Select batching, parallelism, and task ordering for a fleet change. | Intermediate; publicly readable. More parallel execution can increase blast radius and load on shared services. |
| [Ansible Vault](https://docs.ansible.com/ansible/latest/vault_guide/index.html) | Review encrypted-data handling in configuration automation. | Public reference. Intermediate; encryption at rest does not prevent exposure after decryption. |
| [Ansible Molecule](https://docs.ansible.com/projects/molecule/) | Evaluate scenarios for developing and testing Ansible collections, playbooks, and roles. | Intermediate; public documentation. Scenario drivers and targets determine infrastructure, privileges, and cleanup requirements. |
| [Ansible Lint](https://docs.ansible.com/projects/lint/) | Check playbooks and roles for documented quality and maintainability rules. | Intermediate; public documentation. Lint passes do not establish desired-state correctness or successful recovery. |

## Infrastructure state, changes, and tests

Treat state ownership and test design as part of implementation. A preview is evidence of a proposed change, not proof of the resulting service.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform state](https://developer.hashicorp.com/terraform/language/state) | Understand infrastructure mappings and state behavior before designing shared automation. | Public reference. Intermediate; state may contain sensitive data. Protect storage and recovery procedures. |
| [Terraform backends](https://developer.hashicorp.com/terraform/language/backend) | Compare state-backend configuration and documented backend capabilities. | Public reference. Intermediate; locking and authentication differ by backend. Do not assume all backends behave alike. |
| [Terraform state locking](https://developer.hashicorp.com/terraform/language/state/locking) | Understand concurrent-run protection and when backend locking is available. | Intermediate; public reference. Investigate lock ownership before unlocking; a lock is not a state backup. |
| [Terraform plan command](https://developer.hashicorp.com/terraform/cli/commands/plan) | Interpret execution plans and distinguish proposed changes from applied state. | Intermediate; public CLI reference. Plans may contain sensitive data and can become stale as systems change. |
| [Terraform testing](https://developer.hashicorp.com/terraform/language/tests) | Review native test structures for modules and infrastructure workflows. | Public reference. Intermediate; some test arrangements create resources. Read execution and cleanup behavior first. |
| [Terraform module development](https://developer.hashicorp.com/terraform/language/modules/develop) | Design reusable infrastructure modules with clear interfaces and documented responsibility boundaries. | Intermediate; public reference. Version modules and test upgrades against real consumer configurations. |
| [Terraform import](https://developer.hashicorp.com/terraform/language/import) | Bring existing infrastructure into configuration while checking ownership and planned changes. | Intermediate; public reference. Import does not by itself reconstruct an accurate configuration or remove drift. |
| [OpenTofu state documentation](https://opentofu.org/docs/language/state/) | Review state ownership and state-related workflows for OpenTofu-managed infrastructure. | Intermediate; publicly readable. State can hold sensitive attributes; assess the chosen backend's protection and recovery separately. |
| [Pulumi testing guide](https://www.pulumi.com/docs/iac/guides/testing/) | Compare unit, property, and integration approaches for infrastructure expressed as code. | Intermediate; public guide. Provider integration tests can create billable resources and require cleanup. |

## Workflow interfaces and runner trust

Check configuration syntax and the security boundaries around shared workflow code, credentials, and artifact transfer.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [GitHub reusable workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) | Define shared workflow interfaces, inputs, secrets, and calls between repositories. | Intermediate; public documentation. Review secret propagation, environment behavior, permissions, and version pinning. |
| [GitHub Actions OpenID Connect](https://docs.github.com/en/actions/concepts/security/openid-connect) | Evaluate identity federation between workflows and external providers. | Advanced; public conceptual guide. Trust policy must bind the intended repository and execution context, not merely the identity provider. |
| [GitHub self-hosted runners](https://docs.github.com/en/actions/concepts/runners/self-hosted-runners) | Assess responsibility for runner machines and their execution environments. | Intermediate; public documentation. Untrusted jobs, persistent workspaces, network reachability, and patching require deliberate controls. |
| [GitHub workflow artifacts](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflow-artifacts) | Understand how outputs move between jobs and remain available after workflow execution. | Foundation onward; public documentation. Retention, access, and storage limits depend on service settings and account terms. |
| [GitHub Actions security guidance](https://docs.github.com/en/actions/security-for-github-actions) | Review workflow, dependency, runner, and credential security considerations. | Public reference. Intermediate; apply the guidance to the repository trust model and runner arrangement. |
| [GitLab CI/CD YAML reference](https://docs.gitlab.com/ci/yaml/) | Check pipeline syntax, job relationships, artifacts, and configuration keywords. | Intermediate; public reference. Match examples to the deployed GitLab version and available features. |
| [GitLab Runner documentation](https://docs.gitlab.com/runner/) | Design and operate execution infrastructure for GitLab pipelines. | Public reference. Advanced; executor choice changes isolation and maintenance responsibilities. |
| [Jenkins Pipeline syntax](https://www.jenkins.io/doc/book/pipeline/syntax/) | Review declarative and scripted Pipeline constructs in maintained build definitions. | Intermediate; public reference. Plugin and agent availability affect which steps a controller can execute. |

## Continue browsing

[Tool directory](toolkit.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Labs, examples, and projects](labs-and-projects.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

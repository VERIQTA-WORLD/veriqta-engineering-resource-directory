# DevOps Automation Engineer: Production Practice Resources

Retries, upgrades, and cleanup are normal operating conditions for automation. Design for them before expanding the consumer base.

## Bound retries and execution

Define retryable failures, attempt limits, and an overall time budget. A retry of a non-idempotent action can duplicate side effects. Prefer confirming the operation result when a timeout leaves completion uncertain.

## Protect consumers during upgrades

Version interfaces and test representative consumers before rollout. Changes to defaults, permissions, output formats, or cleanup behavior can break callers without changing the operation name. Provide an explicit migration route for consequential differences.

## Make reconciliation a supported path

List incomplete operations and the evidence needed to resume, compensate, or escalate. Cleanup automation must respect ownership and resource dependencies. Expiration rules should account for resources still in active use and exceptions that require an owner.

## Operating references

- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows): Inputs, secrets, permissions, and version references. [Access and technical limits](../README.md#source-reuse).
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use): Untrusted input, credentials, and third-party actions. [Access and technical limits](../README.md#source-secure).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html): Module support and the limitations of check mode. [Access and technical limits](../README.md#source-check).

[Back to DevOps Automation Engineer resources](README.md) · [Browse this career collection](../README.md)

# DevOps Architect: Official Documentation

Use these primary references to check the mechanisms behind architecture decisions. Read the relevant implementation section before treating a capability as part of your design.

## Start with a claim that needs validation

Write the proposed behavior precisely: which identity can publish an artifact, what prevents conflicting changes, or how reconciliation is authorized. Link each important claim to the applicable reference and release. A product homepage cannot validate a detailed permission or recovery assumption.

## Track documentation and local configuration separately

Default behavior, account-level controls, integration settings, and workload configuration can all affect the result. Keep a small claim-to-evidence record. Documentation establishes supported behavior; inspection and controlled tests establish how your system is configured.

## Escalate gaps explicitly

If the architecture depends on a behavior you cannot confirm, mark it unresolved and identify a test or specialist review. Do not turn uncertainty into a promise. Revisit the decision if implementation or service constraints make the required behavior impractical.

## References to check against your configuration

- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use): Untrusted input, credentials, and third-party actions. [Access and technical limits](../README.md#source-secure).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [SLSA specification](https://slsa.dev/spec/): Threats, tracks, and provenance concepts in the selected specification version. [Access and technical limits](../README.md#source-slsa).
- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/): Permission concepts and policy integration. [Access and technical limits](../README.md#source-permissions).

## A concrete documentation review

Select five consequential claims from your design. For each, record the reference section, local setting, applicable version, proposed validation, and owner of any unresolved question.

[Back to DevOps Architect resources](README.md) · [Browse this career collection](../README.md)

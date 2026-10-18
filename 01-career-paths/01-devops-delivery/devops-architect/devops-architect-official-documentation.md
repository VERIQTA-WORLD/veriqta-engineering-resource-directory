# DevOps Architect: Official Documentation

Use these primary references to check the mechanisms behind architecture decisions. Read the relevant implementation section before treating a capability as part of your design.

This page focuses on designing a coherent delivery and operating system across applications, infrastructure, identity, observability, and ownership. **Question to keep in view:** Which boundaries and controls let teams release independently without losing operating accountability?

## On this page

- [Start with a claim that needs validation](#start-with-a-claim-that-needs-validation)
- [Track documentation and local configuration separately](#track-documentation-and-local-configuration-separately)
- [Escalate gaps explicitly](#escalate-gaps-explicitly)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Start with a claim that needs validation

Write the proposed behavior precisely: which identity can publish an artifact, what prevents conflicting changes, or how reconciliation is authorized. Link each important claim to the applicable reference and release. A product homepage cannot validate a detailed permission or recovery assumption.

## Track documentation and local configuration separately

Default behavior, account-level controls, integration settings, and workload configuration can all affect the result. Keep a small claim-to-evidence record. Documentation establishes supported behavior; inspection and controlled tests establish how your system is configured.

## Escalate gaps explicitly

If the architecture depends on a behavior you cannot confirm, mark it unresolved and identify a test or specialist review. Do not turn uncertainty into a promise. Revisit the decision if implementation or service constraints make the required behavior impractical.

## Build a claim-to-evidence record

Write the claim you need to validate, identify the applicable reference section and release, then inspect the actual local setting. Use a controlled test when configuration or integration behavior remains uncertain. Keep unsupported assumptions visible. A published capability and a working local control are different pieces of evidence.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use)

**Use it to answer:** Can untrusted input or a dependency influence a job that holds consequential authority?

- **Start with:** Untrusted input, credentials, and third-party actions.
- **Prerequisites:** Understanding of triggers, jobs, and runner access.
- **Access and limits:** See the [maintained source annotation](../README.md#source-secure) for publisher context, access conditions, and the key limitation.

### [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking)

**Use it to answer:** What evidence distinguishes a currently active operation from an abandoned lock?

- **Start with:** Lock behavior and force-unlock conditions.
- **Prerequisites:** Understanding of the selected backend and active operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-locking) for publisher context, access conditions, and the key limitation.

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

**Use it to answer:** Which policy layers determine whether the execution identity can perform the requested action?

- **Start with:** Policy types and the linked evaluation guidance.
- **Prerequisites:** AWS identities, resources, and basic JSON familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-iam) for publisher context, access conditions, and the key limitation.

### [SLSA specification](https://slsa.dev/spec/)

**Use it to answer:** What evidence links the artifact to the source and build process, and what trust remains outside that evidence?

- **Start with:** Threats, tracks, and provenance concepts in the selected specification version.
- **Prerequisites:** Build systems and artifact trust concepts.
- **Access and limits:** See the [maintained source annotation](../README.md#source-slsa) for publisher context, access conditions, and the key limitation.

### [Backstage permissions overview](https://backstage.io/docs/permissions/overview/)

**Use it to answer:** Where is the permission decision enforced and which plugin or downstream action must respect it?

- **Start with:** Permission concepts and policy integration.
- **Prerequisites:** Backend development and authentication familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-permissions) for publisher context, access conditions, and the key limitation.

## Apply the reading

Select five consequential claims from your design. For each, record the reference section, local setting, applicable version, proposed validation, and owner of any unresolved question.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

## Sources and review scope

Prepared for VERIQTA on 18 October 2026. The linked primary-source entry pages were opened and reviewed for identity, scope, and the navigation supporting this selection. Full manuals, linked courses, and downstream examples were not reviewed in their entirety. No exercises or production changes were executed for this collection. Examples, project briefs, and decision aids are original VERIQTA editorial guidance. Use the applicable product version; access and hosted-service conditions can change.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

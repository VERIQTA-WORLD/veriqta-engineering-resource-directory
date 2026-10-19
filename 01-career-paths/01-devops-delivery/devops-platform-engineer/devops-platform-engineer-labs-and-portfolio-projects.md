# DevOps Platform Engineer: Labs and Portfolio Projects

## Define a supported onboarding contract

Choose one fictional developer team and one routine onboarding task.

Produce a user journey, contract, responsibility table, supported inputs, failure states, and consumer acceptance checks.

### Environment and access

A design-only exercise needs no portal or cloud account. Use synthetic teams, services, and identities.

### Challenge the result

Assume artifact generation succeeds but downstream authorization fails. Define status, ownership, and reconciliation without hiding partial work.

A design review does not establish usability; a consumer trial and implementation evidence are separate work.

### Cleanup

Remove optional prototypes and credentials. Retain the contract and its unresolved validation questions.

### Implementation resources

- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) · [Access and limitations](../README.md#source-platforms)
- [C4 model](https://c4model.com/) · [Access and limitations](../README.md#source-c4)
- [Architecture Decision Records](https://adr.github.io/) · [Access and limitations](../README.md#source-adr)

## Connect catalog metadata to a template

Explore one catalog entity and a small template in a local Backstage learning environment.

Record service ownership metadata, input validation, generated artifacts, action authority, and the expected consumer result.

### Environment and access

Use the prerequisites and installation guidance linked from current Backstage documentation. External actions need explicitly configured integrations.

### Challenge the result

Use only synthetic destinations. Test an invalid owner or missing input and record how the user and operator discover the issue.

Catalog ownership metadata alone does not grant or restrict external execution authority.

### Cleanup

Stop local services and remove dedicated generated artifacts. Revoke test integration credentials and remove any generated external repositories.

### Implementation resources

- [Backstage Software Catalog](https://backstage.io/docs/features/software-catalog/) · [Access and limitations](../README.md#source-catalog)
- [Backstage Software Templates](https://backstage.io/docs/features/software-templates/) · [Access and limitations](../README.md#source-templates)
- [Backstage authentication](https://backstage.io/docs/auth/) · [Access and limitations](../README.md#source-auth)

## Test a permission boundary and workflow upgrade

Design two consumers with different authority to request a shared delivery operation.

Produce an allow/deny matrix, enforcement map, versioned workflow contract, compatibility examples, and upgrade communication.

### Environment and access

Begin design-only. An implementation needs a disposable repository or local platform with compatible permission integration.

### Challenge the result

Test a denied request and an interrupted authorized action. Then change one output contract and assess existing consumers.

Passing one permission test does not prove every plugin or downstream integration enforces the same boundary.

### Cleanup

Remove test identities, credentials, triggers, and dedicated resources. Preserve sanitized denied and allowed observations separately.

### Implementation resources

- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/) · [Access and limitations](../README.md#source-permissions)
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) · [Access and limitations](../README.md#source-reuse)
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use) · [Access and limitations](../README.md#source-secure)

[Back to DevOps Platform Engineer resources](README.md) · [Browse this career collection](../README.md)

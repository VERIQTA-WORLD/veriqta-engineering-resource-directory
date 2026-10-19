# Platform Reliability Engineer: Labs and Portfolio Projects

## Model a partial consumer operation

Design onboarding that creates one external resource before losing its status response.

### Set up the exercise

Use synthetic requests and resource records first. An optional implementation must use owned disposable repositories or local targets.

### Investigate the behavior

Replay the same request and a conflicting request. Define how the existing resource is found without crossing a tenant boundary.

Produce request identity rules, state transitions, permission decisions, consumer status, reconciliation, and acceptance tests.

### Finish and clean up

Remove generated test resources and temporary identities. Preserve sanitized evidence and source references, not credentials.

### References for this project

- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) · [Prerequisites and limitations](../README.md#source-platforms)
- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/) · [Prerequisites and limitations](../README.md#source-permissions)
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Prerequisites and limitations](../README.md#source-state)

## Review a shared workflow upgrade

Expose a small synthetic validation task to two consumer repositories and assess a contract change.

### Set up the exercise

Use disposable repositories, bounded permissions, current reusable-workflow instructions, and account-aware runner usage.

### Investigate the behavior

Change one output or required permission in a new version. Test an allowed caller, a denied caller, and a failed execution.

Keep the consumer contract, version references, expected and actual results, migration note, and support route.

### Finish and clean up

Disable scheduled execution, remove disposable repositories or integrations, and revoke temporary secrets.

### References for this project

- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) · [Prerequisites and limitations](../README.md#source-reuse)
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use) · [Prerequisites and limitations](../README.md#source-secure)
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/) · [Prerequisites and limitations](../README.md#source-slo)

[Back to Platform Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

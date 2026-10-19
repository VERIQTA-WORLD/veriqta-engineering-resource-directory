# Platform Reliability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for operating shared developer capabilities with explicit tenant boundaries, consumer objectives, and recoverable workflows. Match the installed version and actual configuration before interpreting an observation.

## Where is the permission decision enforced?

Check the installed plugin, policy integration, executor, and external-system authority.

Read [Backstage permissions overview](https://backstage.io/docs/permissions/overview/), starting with permission concepts and policy integration. Each plugin and downstream action needs appropriate enforcement; UI visibility alone is insufficient.

## What authority reaches a shared workflow?

Inspect caller permissions, secrets, inputs, and called workflow configuration.

Read [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows), starting with inputs, secrets, permissions, and version references. Sharing execution logic also creates compatibility and rollout responsibilities.

## What external resources does the controller manage?

Compare operation identity, tracked resources, and actual partial effects after interruption.

Read [Terraform: State](https://developer.hashicorp.com/terraform/language/state), starting with the purpose of state and its relationship to resources. State may contain sensitive values; its storage and access need explicit controls.

## Related implementation references

- [Backstage authentication](https://backstage.io/docs/auth/): Authentication architecture and your selected provider. [Access and technical limits](../README.md#source-auth).

[Back to Platform Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

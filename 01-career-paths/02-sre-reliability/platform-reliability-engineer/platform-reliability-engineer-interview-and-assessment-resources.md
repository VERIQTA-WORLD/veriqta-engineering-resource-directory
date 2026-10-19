# Platform Reliability Engineer: Interview and Assessment Resources

These scenarios test whether you can explain the consumer contract when shared execution becomes uncertain.

## Portal healthy, deployments stalled

Explain the missing service indicator and trace the request through authorization, queueing, executor credentials, and external actions. Propose the next discriminating observation and a safe consumer response.

## Retries create two environments

Explain operation identity, state ownership, and reconciliation. Compare retrying execution with checking existing external state. Identify which consumer and tenant authority must be preserved during recovery.

## What to look for in your answer

Distinguish accepted work from useful completion. Explain how an operator and a consumer discover partial effects without creating duplicates or crossing tenant authority.

## References for checking the reasoning

- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/) · [Access and technical limits](../README.md#source-permissions)
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) · [Access and technical limits](../README.md#source-reuse)
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Access and technical limits](../README.md#source-state)
- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/) · [Access and technical limits](../README.md#source-platforms)

[Back to Platform Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

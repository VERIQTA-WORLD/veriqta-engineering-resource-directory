# Platform Reliability Engineer: Role and Responsibility Resources

Platform reliability is the ability of consumers to complete supported tasks, including when a shared integration fails halfway through.

## Define consumer-visible reliability

Measure supported tasks such as onboarding, deployment, or environment creation through useful completion. A responsive portal can coexist with a failed executor. Define the boundary and denominator so rejected, queued, and partially completed requests remain visible.

## Own shared failure behavior

Document how identity, policy, controllers, external integrations, and state interact. Keep tenant authority scoped. A retry after lost status must not silently duplicate external effects or give one tenant access to another tenant’s resources.

## Support lifecycle and compatibility

Assign owners for template changes, shared workflow versions, integration upgrades, and retirement. Platform reliability includes the period after generation. Consumers need a stable contract and a support route when shared behavior changes.

## Resources behind these responsibilities

- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/): Platform capabilities and the platform-as-product discussion. [Access and technical limits](../README.md#source-platforms).
- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/): Permission concepts and policy integration. [Access and technical limits](../README.md#source-permissions).
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows): Inputs, secrets, permissions, and version references. [Access and technical limits](../README.md#source-reuse).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).

[Back to Platform Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

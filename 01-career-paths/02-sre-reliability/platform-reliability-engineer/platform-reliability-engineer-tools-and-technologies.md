# Platform Reliability Engineer: Tools and Technology Resources

The platform interface and the capability behind it need different evidence. Monitor the task, not just the page that starts it.

## Separate the interface from the capability

Catalogs and templates can improve discovery and setup, while permission systems and executors control actions. Evaluate each component against the consumer contract. Avoid installing a portal when a supported repository workflow meets the need with less operating burden.

## Use operation and dependency signals

Track request acceptance, queue age, execution status, external resource identity, and useful completion. Correlate these stages without exposing secrets. Alerting on portal availability alone misses failures in the platform’s actual service.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Consumer operation telemetry | Use it to connect acceptance, queueing, execution, and useful completion. | Portal health alone can hide a failed task or accumulating work. |
| Permission enforcement | Use it at the action boundary that controls external effects. | Check plugin integration and downstream identity; separate UI views do not establish tenant isolation. |
| Versioned shared workflow | Use it to provide a supported contract across consumers. | Compatibility changes can break existing services after successful onboarding. |

## Implementation and diagnostic references

- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/): Permission concepts and policy integration. [Access and technical limits](../README.md#source-permissions).
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows): Inputs, secrets, permissions, and version references. [Access and technical limits](../README.md#source-reuse).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).

## Reading behind the tool decision

- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/): Platform capabilities and the platform-as-product discussion. [Access and technical limits](../README.md#source-platforms).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).

[Back to Platform Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

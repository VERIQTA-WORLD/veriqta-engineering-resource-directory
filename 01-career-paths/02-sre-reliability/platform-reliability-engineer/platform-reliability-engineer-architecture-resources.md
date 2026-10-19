# Platform Reliability Engineer: Architecture Resources

A shared operation needs a discoverable result and a tenant-aware reconciliation path when its caller loses the response.

## Design durable status and reconciliation

Give each consequential request a discoverable identity. Define how partial completion is resumed, compensated, or handed to an operator. Record which component owns state and which external effects can outlive the requester or worker.

## Contain shared dependencies

Compare tenant-scoped authority, concurrency controls, capacity allocation, and versioned interfaces. Define how a credential or controller failure affects consumers. Protect response and recovery paths from the same dependency where feasible.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/): Platform capabilities and the platform-as-product discussion. [Access and technical limits](../README.md#source-platforms).
- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/): Permission concepts and policy integration. [Access and technical limits](../README.md#source-permissions).
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows): Inputs, secrets, permissions, and version references. [Access and technical limits](../README.md#source-reuse).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).

[Back to Platform Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

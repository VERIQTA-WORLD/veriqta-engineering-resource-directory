# Platform Reliability Engineer: Skills and Prerequisite Resources

Separate catalog information, requester identity, executor authority, operation state, and downstream resource ownership.

## Trace a consumer operation

Follow authentication, authorization, input validation, execution, downstream side effects, status, and verification. Distinguish catalog metadata from authoritative execution state. Learn how callers discover a result after the interface loses its connection.

## Understand tenancy and shared state

Identify shared credentials, runners, controllers, state stores, and capacity. Evaluate both unauthorized access and noisy-neighbor failure. A separate page or namespace is only one boundary and may not provide the isolation the service requires.

## Read at the boundary you need to understand

- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/): Platform capabilities and the platform-as-product discussion. [Access and technical limits](../README.md#source-platforms).
- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/): Permission concepts and policy integration. [Access and technical limits](../README.md#source-permissions).
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows): Inputs, secrets, permissions, and version references. [Access and technical limits](../README.md#source-reuse).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).
- [Backstage authentication](https://backstage.io/docs/auth/): Authentication architecture and your selected provider. [Access and technical limits](../README.md#source-auth).

[Back to Platform Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

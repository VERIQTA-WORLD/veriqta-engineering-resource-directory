# DevOps Platform Engineer: Tools and Technology Resources

A catalog helps you find a service. A template can create artifacts. Neither automatically provides a dependable deployment capability.

## Separate discoverability from execution

A catalog can help users find services and owners. A template can generate artifacts or call integrations. Neither automatically establishes runtime access or operating accountability. Choose the smallest interface that lets users complete the intended task reliably.

## Make integration authority explicit

Review the identity and permission scope used by each action. Keep consumer authorization separate from executor credentials. Validate external side effects and provide a way to discover partial completion after a frontend or backend failure.

## Choose a manageable service footprint

Every new component adds upgrades, configuration, credentials, and incident work. A repository template or reusable workflow may satisfy an early need with less operating burden than a full portal. Reassess when usage and support evidence justify more capability.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Backstage catalog | Use it to expose service metadata and ownership. | Stale catalog metadata does not become an authorization decision. |
| Software Templates | Use templates to guide a supported creation task. | Review input validation and every action’s external authority and residual effects. |
| Reusable delivery workflows | Use them when teams need common behavior without a full portal. | Keep the consumer contract versioned and explain which responsibilities remain with the application team. |

## Implementation and diagnostic references

- [Backstage Software Catalog](https://backstage.io/docs/features/software-catalog/): Entity concepts and ownership information. [Access and technical limits](../README.md#source-catalog).
- [Backstage Software Templates](https://backstage.io/docs/features/software-templates/): Template structure and available actions. [Access and technical limits](../README.md#source-templates).
- [Backstage permissions overview](https://backstage.io/docs/permissions/overview/): Permission concepts and policy integration. [Access and technical limits](../README.md#source-permissions).
- [GitHub Actions: Reuse workflows](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows): Inputs, secrets, permissions, and version references. [Access and technical limits](../README.md#source-reuse).
- [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/): Core concepts, then the relevant user guide. [Access and technical limits](../README.md#source-argo).

[Back to DevOps Platform Engineer resources](README.md) · [Browse this career collection](../README.md)

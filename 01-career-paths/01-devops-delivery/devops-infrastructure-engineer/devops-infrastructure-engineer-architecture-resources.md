# DevOps Infrastructure Engineer: Architecture Resources

The repair path deserves its own diagram. It may fail with the environment even when the application design has redundancy.

## Map the control plane

Show where definitions, state, credentials, runners, and configuration inventories live. Identify dependencies needed to perform a change. If the recovery process depends on a service inside the failed environment, provide a credible alternate route.

## Define state and failure boundaries

Separate environments or resource groups according to ownership and impact where justified. Smaller boundaries can reduce blast radius but introduce coordination and dependency management. Compare options using actual change patterns and recovery requirements.

## Account for persistent data

Document which resources hold valuable data and which references merely recreate empty capacity. Review deletion protection, retention, restore authority, and service acceptance with the data owner. A reproducible environment is not a substitute for a verified restore.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html): The framework overview and the pillar relevant to your review. [Access and technical limits](../README.md#source-aws).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

# DevOps Consultant: Architecture Resources

A target architecture needs a route from the current system, including who can support each stage after you leave.

## Map the current delivery boundary

Show people, systems, permissions, and external dependencies that affect a representative change. Mark confirmed relationships separately from assumptions. The purpose is to locate constraints and risks, not to create an exhaustive diagram of every installed product.

## Design a staged transition

Select a pilot boundary with a willing owner and a manageable recovery path. Explain which interfaces remain unchanged and where temporary duplication is necessary. Include a decision point for stopping or revising the migration when evidence does not support expansion.

## Transfer decision ownership

Record alternatives, rejected options, validation results, and unresolved dependencies. Have client maintainers review the design through realistic failure scenarios. A handover should let them reason about future changes rather than merely reproduce your setup.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [arc42](https://arc42.org/): The template overview and quality requirements. [Access and technical limits](../README.md#source-arc).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/): Platform capabilities and the platform-as-product discussion. [Access and technical limits](../README.md#source-platforms).
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html): The framework overview and the pillar relevant to your review. [Access and technical limits](../README.md#source-aws).

[Back to DevOps Consultant resources](README.md) · [Browse this career collection](../README.md)

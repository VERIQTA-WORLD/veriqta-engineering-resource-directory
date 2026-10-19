# DevOps Engineer: Architecture Resources

Draw the deployment path and the user request path separately, then identify where configuration, identity, and artifact versions connect them.

## Draw two connected paths

Show how a source change becomes a deployed artifact and how a user request reaches the running service. Connect them through configuration, identity, and version information. This prevents a pipeline-only view of service acceptance.

## Design environment differences deliberately

List which differences are required, such as credentials and capacity, and which are accidental. Make configuration sources and ownership explicit. Similar manifests do not guarantee similar behavior when dependencies, data, or policies differ.

## Include a practical recovery route

State how you select a previous artifact, verify compatibility, and assess user impact. Identify data changes that cannot be undone by redeployment. Keep the recovery route within the access and skills available to the responder.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Canarying Releases](https://sre.google/workbook/canarying-releases/): Canary design, comparison signals, and decision criteria. [Access and technical limits](../README.md#source-canary).
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html): The framework overview and the pillar relevant to your review. [Access and technical limits](../README.md#source-aws).

[Back to DevOps Engineer resources](README.md) · [Browse this career collection](../README.md)

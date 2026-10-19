# DevOps Architect: Skills and Prerequisite Resources

Before you defend a delivery design, you need to follow the artifact, the request, the permission decision, and the recovery dependency.

## Develop implementation literacy

You should be able to trace a process, a request, an artifact, and a permission decision. Use a small implementation to expose uncertainty in your mental model. You do not need equal depth in every tool, but you need to know when a specialist review is necessary.

## Reason about state and failure

Distinguish source history, desired configuration, infrastructure state, persistent application data, and runtime status. They change through different mechanisms. A rollback plan that treats all five as the same object can restore a manifest while leaving the service unusable.

## Communicate constraints precisely

Practise expressing availability, isolation, recovery, and cost as conditions a design can be evaluated against. Learn to separate a requirement from an implementation preference. Record what is unknown instead of concealing it with a detailed diagram.

## Read at the boundary you need to understand

- [Pro Git, second edition](https://git-scm.com/book/en/v2): Git Basics, then branching and the internals relevant to your question. [Access and technical limits](../README.md#source-git).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Kubernetes overview](https://kubernetes.io/docs/concepts/overview/): What Kubernetes does and the linked concepts. [Access and technical limits](../README.md#source-kube).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [arc42](https://arc42.org/): The template overview and quality requirements. [Access and technical limits](../README.md#source-arc).

[Back to DevOps Architect resources](README.md) · [Browse this career collection](../README.md)

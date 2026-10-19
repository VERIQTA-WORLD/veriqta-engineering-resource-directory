# DevOps Engineer: Official Documentation

Use these references to confirm workflow, runtime, and permission behavior while implementing the delivery path. Match each source to the system and release actually in use.

## Read the implementation contract

Check triggers, job permissions, environment configuration, and dependencies before adapting a workflow example. Confirm whether a change can be initiated by untrusted input. Record which settings come from the repository and which are controlled elsewhere.

## Check runtime behavior separately

Use application and platform documentation to understand startup, readiness, service routing, and diagnostic access. A successful deployment API call establishes a different fact from a working user request. Verify each boundary with the appropriate evidence.

## Keep a claim-to-setting map

For consequential behavior, record the reference, local configuration, and proposed test. Examples include deployment approval, artifact selection, target identity, and failure detection. Unknown behavior should remain an explicit question until validated.

## References to check against your configuration

- [GitHub Actions documentation](https://docs.github.com/en/actions): The relevant concepts, how-to guide, and reference for your task. [Access and technical limits](../README.md#source-actions).
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use): Untrusted input, credentials, and third-party actions. [Access and technical limits](../README.md#source-secure).
- [GitHub Actions: Deployment environments](https://docs.github.com/en/actions/concepts/workflows-and-actions/deployment-environments): The environment concept and linked configuration guidance. [Access and technical limits](../README.md#source-env).
- [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/): The guide matching the failing application boundary. [Access and technical limits](../README.md#source-debug).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).

## A concrete documentation review

Review an existing workflow without changing it. Identify the source trigger, executor identity, artifact reference, destination, and acceptance evidence. Note any authority that the configuration does not make clear.

[Back to DevOps Engineer resources](README.md) · [Browse this career collection](../README.md)

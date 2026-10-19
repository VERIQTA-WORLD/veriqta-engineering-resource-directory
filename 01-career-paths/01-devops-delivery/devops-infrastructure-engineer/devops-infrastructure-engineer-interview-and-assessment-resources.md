# DevOps Infrastructure Engineer: Interview and Assessment Resources

The difficult infrastructure answer usually depends on state and data ownership, not on remembering a command.

## Prompt: a backend lock blocks a release

A lock error occurs while another engineer may still be operating. Explain the evidence required before any unlock and how you would assess resource changes already in progress. Avoid interpreting elapsed time alone as proof of abandonment.

## Prompt: a plan proposes replacement

A provider update causes a persistent resource to be replaced. Explain how you inspect the reason, data implications, dependencies, and alternatives. Identify the conditions under which you would stop rather than apply.

## Prompt: rebuild succeeded, service failed

Infrastructure recreation completes, but the application cannot use restored data. Separate provisioning, configuration, authorization, restoration, and application compatibility. Describe evidence that narrows the failed boundary.

## What to look for in your answer

Keep state coordination, external resource effects, and valuable data separate. Explain who owns each, what remains uncertain after interruption, and how the workload is verified after reconciliation.

## References for checking the reasoning

- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking) · [Access and technical limits](../README.md#source-locking)
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Access and technical limits](../README.md#source-state)
- [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests) · [Access and technical limits](../README.md#source-tests)
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) · [Access and technical limits](../README.md#source-iam)
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) · [Access and technical limits](../README.md#source-aws)

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

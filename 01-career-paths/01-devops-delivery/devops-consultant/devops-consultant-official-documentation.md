# DevOps Consultant: Official Documentation

Use primary references to validate findings and proposed controls. Keep documented product behavior separate from client configuration, stakeholder expectations, and your interpretation.

## Keep an evidence register

For each finding, record the observation, source, environment, confidence, affected requirement, and open question. Avoid language such as compliant or secure without a defined criterion and assessment scope. Identify findings that depend on unavailable evidence.

## Check actual access conditions

Review policy layers and workflow trust boundaries before requesting or using credentials. Least-privilege inspection may require a different approach from implementation. Consultant access should have an owner, purpose, expiry, and removal record.

## Ground controls in the right reference

Use a security framework to organize responsibilities and product documentation to validate implementation behavior. A framework statement does not prove a configured control works. Where an obligation needs legal interpretation, involve the client's responsible specialist.

## References to check against your configuration

- [NIST SP 800-218: Secure Software Development Framework](https://csrc.nist.gov/pubs/sp/800/218/final): Publication scope and the practice groups relevant to your assessment. [Access and technical limits](../README.md#source-ssdf).
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use): Untrusted input, credentials, and third-party actions. [Access and technical limits](../README.md#source-secure).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).
- [GitHub Actions: Deployment environments](https://docs.github.com/en/actions/concepts/workflows-and-actions/deployment-environments): The environment concept and linked configuration guidance. [Access and technical limits](../README.md#source-env).
- [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking): Lock behavior and force-unlock conditions. [Access and technical limits](../README.md#source-locking).

## A concrete documentation review

Prepare a finding with three separate evidence categories: published behavior, observed configuration, and a controlled validation still needed. Include how the conclusion would change if the validation fails.

[Back to DevOps Consultant resources](README.md) · [Browse this career collection](../README.md)

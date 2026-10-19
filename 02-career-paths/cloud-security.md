# Cloud Security Engineering

Start by identifying who can act, which resources they can affect, and where your data moves. Choose provider-specific references for the environment you actually use.

## Begin with identity

**[AWS IAM policies and permissions →](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)**  
Understand the policy types and evaluation context behind an allowed or denied AWS action.  
**Free documentation · Intermediate · AWS identity familiarity helpful**

For an AWS workload review, the **[AWS Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)** connects protection concerns across the workload. It is free to read; implementation and exercises can create charges.

## Use the reference for your provider

| Environment | Resource | What to check |
| --- | --- | --- |
| AWS | [AWS security guidance](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html) | Workload responsibilities and the relevant service configuration |
| Azure | [Microsoft cloud security benchmark](https://learn.microsoft.com/en-us/security/benchmark/azure/overview) | Control guidance and version status; the v2 overview is marked preview |
| Google Cloud | [Security Best Practices Center](https://cloud.google.com/security/best-practices) | The identity, data, or workload guide matching your task |

These are publicly readable references. Follow their service-specific requirements before making changes.

## Trace the resources you manage

<table>
<tr>
<td align="center"><a href="../04-tools/terraform.md"><img src="../assets/logos/terraform.svg" width="48" height="48" alt="Terraform"/><br/>Terraform</a></td>
<td align="center"><a href="../04-tools/opentofu.md"><img src="../assets/logos/opentofu.svg" width="48" height="48" alt="OpenTofu"/><br/>OpenTofu</a></td>
</tr>
</table>


[Security topics](../03-topics/security.md) · [Networking](../03-topics/networking.md) · [Cloud platforms](../05-cloud-platforms/)

Infrastructure definitions help you inspect intended resources. Verify effective permissions and actual configuration separately.

## Practise an access boundary

In a dedicated learning scope, define an identity that can perform one intended action and is denied a related action outside its scope. Use synthetic data, preserve the policy and result, and remove temporary identities, keys, and resources afterward. Inspect current costs before provisioning.

[Find labs →](../06-practice/labs.md) · [Investigate cloud failures →](../07-troubleshooting/cloud.md)

For build and deployment controls, continue to [DevSecOps](devsecops.md). For workload foundations, use [cloud engineering](cloud-engineering.md).

[All career paths](README.md) · [Directory homepage](../README.md)

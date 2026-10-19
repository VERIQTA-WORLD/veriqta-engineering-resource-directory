# Cloud Security Engineering

Start by identifying who can act, which resources they can affect, and where your data moves. Choose provider-specific references for the environment you actually use.

## Begin with identity

**[AWS IAM policies and permissions →](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)**  
Understand the policy types and evaluation context behind an allowed or denied AWS action.  
**Free documentation · Intermediate · AWS identity familiarity helpful**

If you are new to provider identities and networks, begin with [cloud engineering](cloud-engineering.md). For this path, you should be able to explain who can act, how that authority is constrained, and which evidence supports your conclusion.

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
<td align="center"><a href="https://developer.hashicorp.com/terraform/tutorials"><img src="../assets/logos/terraform.svg" width="48" height="48" alt="Terraform"/><br/>Terraform</a></td>
<td align="center"><a href="https://opentofu.org/docs/"><img src="../assets/logos/opentofu.svg" width="48" height="48" alt="OpenTofu"/><br/>OpenTofu</a></td>
</tr>
</table>

Infrastructure definitions help you inspect intended resources. Verify effective permissions and actual configuration separately.

## Check a policy before granting access

Use [AWS’s IAM policy simulator guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) to compare an intended action with an action that should be denied. Read its permissions requirements and simulator limitations first; account access is required.

Record the principal, action, resource, supplied context, and expected decision. Explain the statement behind each result. Simulation does not send the real service request, and its decisions can differ from your live environment.

If you proceed to live verification, use synthetic data in a dedicated learning scope with an authorized identity. Confirm both the allowed and denied cases, then remove temporary policies, identities, and resources. A screenshot of an allowed request alone does not demonstrate the boundary.

For build and deployment controls, continue to [DevSecOps](devsecops.md). For workload foundations, use [cloud engineering](cloud-engineering.md).

[All career paths](README.md) · [Directory homepage](../README.md)

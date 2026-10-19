# Cloud Engineering

Choose one provider first. Learn how an application uses identity, networking, compute, storage, and monitoring within it; expand to another provider when your work gives you a reason.

## Pick your provider

| Provider | Official learning route | Before you commit |
| --- | --- | --- |
| **AWS** | [AWS Skill Builder](https://skillbuilder.aws/) — browse training for your current AWS task | Check sign-in, subscription, and lab access for the selected offering |
| **Microsoft Azure** | [Azure training on Microsoft Learn](https://learn.microsoft.com/en-us/training/azure/) — choose a relevant module or learning path | Reading and practical exercise access are different; inspect subscription requirements |
| **Google Cloud** | [Google Cloud training](https://cloud.google.com/learn/training) — compare courses, learning paths, and labs | Check accounts, credits, and paid access before starting a lab |

[AWS collection](../05-cloud-platforms/aws.md) · [Azure collection](../05-cloud-platforms/azure.md) · [Google Cloud collection](../05-cloud-platforms/google-cloud.md)

## Learn the boundaries together

| You need to understand… | Explore |
| --- | --- |
| How traffic reaches the workload | [Networking](../03-topics/networking.md) |
| How access is granted and constrained | [Security](../03-topics/security.md) |
| How environments are defined and changed | [Infrastructure as Code](../03-topics/infrastructure-as-code.md) |
| How you observe and recover the workload | [Observability](../03-topics/observability.md) · [Reliability](../03-topics/reliability.md) |

## Automate once you understand the resource

<table>
<tr>
<td align="center"><a href="../04-tools/terraform.md"><img src="../assets/logos/terraform.svg" width="48" height="48" alt="Terraform"/><br/>Terraform</a></td>
<td align="center"><a href="../04-tools/opentofu.md"><img src="../assets/logos/opentofu.svg" width="48" height="48" alt="OpenTofu"/><br/>OpenTofu</a></td>
<td align="center"><a href="../04-tools/ansible.md"><img src="../assets/logos/ansible.svg" width="48" height="48" alt="Ansible"/><br/>Ansible</a></td>
</tr>
</table>


Use the relevant tool collection after you can explain the provider resource, required permissions, and expected cost. You do not need to learn both Terraform and OpenTofu to begin.

## A useful first cloud project

Deploy a small application in a dedicated learning scope. Verify access, connectivity, and one functional request. Inventory billable resources before creation; remove compute, storage, addresses, and temporary access according to the provider instructions afterward. Check for resources that survive the main teardown.

[Find cloud projects →](../06-practice/projects.md) · [Explore cloud failures →](../07-troubleshooting/cloud.md)

For access and protection work, continue to [cloud security](cloud-security.md).

[All career paths](README.md) · [Directory homepage](../README.md)

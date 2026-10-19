# Cloud Engineering

Choose one provider first. Learn how an application uses identity, networking, compute, storage, and monitoring within it; expand to another provider when your work gives you a reason.

## Pick your provider

| Provider | Official learning route | Before you commit |
| --- | --- | --- |
| **AWS** | [AWS Skill Builder](https://skillbuilder.aws/) — browse training for your current AWS task | Check sign-in, subscription, and lab access for the selected offering |
| **Microsoft Azure** | [Azure training on Microsoft Learn](https://learn.microsoft.com/en-us/training/azure/) — choose a relevant module or learning path | Reading and practical exercise access are different; inspect subscription requirements |
| **Google Cloud** | [Google Cloud training](https://cloud.google.com/learn/training) — compare courses, learning paths, and labs | Check accounts, credits, and paid access before starting a lab |


## Learn the boundaries together

| You need to understand… | Explore |
| --- | --- |
| How traffic reaches the workload | [Networking](network-engineering.md) |
| How access is granted and constrained | [Cloud security](cloud-security.md) |
| How environments are defined and changed | [Infrastructure as Code](https://developer.hashicorp.com/terraform/tutorials) |
| How you observe and recover the workload | [Observability](observability.md) · [Reliability](sre.md) |

## Automate once you understand the resource

<table>
<tr>
<td align="center"><a href="https://developer.hashicorp.com/terraform/tutorials"><img src="../assets/logos/terraform.svg" width="48" height="48" alt="Terraform"/><br/>Terraform</a></td>
<td align="center"><a href="https://opentofu.org/docs/"><img src="../assets/logos/opentofu.svg" width="48" height="48" alt="OpenTofu"/><br/>OpenTofu</a></td>
<td align="center"><a href="https://docs.ansible.com/projects/ansible/latest/getting_started/index.html"><img src="../assets/logos/ansible.svg" width="48" height="48" alt="Ansible"/><br/>Ansible</a></td>
</tr>
</table>

Use the relevant documentation after you can explain the provider resource, required permissions, and expected cost. You do not need to learn both Terraform and OpenTofu to begin.

## Choose a project you can remove

Pick a compute or application-deployment exercise from your provider’s learning route above. Read its account, region, subscription, and lab-access requirements before creating anything. The exercise should cover one application, its identity, its network path, and its logs.

Draw those dependencies and mark which resources can cost money while idle. Keep a successful request, one explained access failure, and the deletion steps with your notes. Then delete the workload and check separately for retained disks, snapshots, addresses, and logging storage.

For your next pass, choose one provider-specific exercise from the [Terraform tutorial catalog](https://developer.hashicorp.com/terraform/tutorials). Compare the planned changes with the resources you previously created manually. Reading is free; provisioned infrastructure can incur charges.

For access and protection work, continue to [cloud security](cloud-security.md).

[All career paths](README.md) · [Directory homepage](../README.md)

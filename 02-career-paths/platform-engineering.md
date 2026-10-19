# Platform Engineering

Start with a task another engineering team needs to finish: create a service, deploy a change, request an environment, or find its owner. Look for resources that help you make that task usable and supportable.

## Understand the capability before choosing the portal

**[CNCF Platforms White Paper →](https://tag-app-delivery.cncf.io/whitepapers/platforms/)**  
Explore platform capabilities, user needs, and the organizational work behind a shared engineering service.  
**Free · White paper · Delivery and operations familiarity helpful**

**[Backstage Software Templates →](https://backstage.io/docs/features/software-templates/)**  
See how scaffolding can generate components and invoke actions; examine inputs and integration authority before adding external actions.  
**Free documentation · Intermediate · A configured Backstage environment is needed for practice**

**[GitHub Actions: Reuse workflows →](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows)**  
Study a smaller shared capability: common workflow logic with defined inputs, outputs, permissions, and consumers.  
**Free documentation · Intermediate · Repository access and runner conditions apply**

## Decide whether a shared capability is worth building

Look for a task several teams repeat and struggle to maintain. A shared workflow introduces versioning, support, and ownership work; compare that cost with the duplication it removes. Start with one consumer journey before choosing a portal.

## Pick the workflow you need to support

| Consumer task | Start here |
| --- | --- |
| Generate a service and a delivery path | [CI/CD](https://dora.dev/capabilities/continuous-delivery/) |
| Provision a supported environment | [Infrastructure as Code](https://developer.hashicorp.com/terraform/tutorials) |
| Deploy and reconcile applications | [GitOps](https://argo-cd.readthedocs.io/en/stable/getting_started/) |
| Investigate the platform’s own failures | [Observability](observability.md) |

<table>
<tr>
<td align="center"><a href="https://docs.github.com/en/actions"><img src="../assets/logos/githubactions.svg" width="48" height="48" alt="GitHub Actions"/><br/>GitHub Actions</a></td>
<td align="center"><a href="https://developer.hashicorp.com/terraform/tutorials"><img src="../assets/logos/terraform.svg" width="48" height="48" alt="Terraform"/><br/>Terraform</a></td>
<td align="center"><a href="https://argo-cd.readthedocs.io/en/stable/getting_started/"><img src="../assets/logos/argo.svg" width="48" height="48" alt="Argo CD"/><br/>Argo CD</a></td>
<td align="center"><a href="https://kubernetes.io/docs/concepts/overview/"><img src="../assets/logos/kubernetes.svg" width="48" height="48" alt="Kubernetes"/><br/>Kubernetes</a></td>
</tr>
</table>

## Make one developer task easier

Begin with a [reusable GitHub Actions workflow](https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows) if your teams already use Actions. Define its inputs, permissions, outputs, and failure messages. Try it from two disposable repositories: can both consume it without copying the implementation?

For a scaffolding task, use [Backstage’s Writing Templates guide](https://backstage.io/docs/features/software-templates/writing-templates/) instead. It assumes a working Backstage installation and relevant integration permissions; it is a larger starting commitment.

Keep the consumer instructions, an example failure, and the supported upgrade path. Ask a colleague to attempt the task without your help. Their points of confusion tell you what to improve. Remove generated repositories, test infrastructure, and temporary integration tokens.

Continue to [DevOps](devops.md) for delivery implementation or [SRE](sre.md) for shared-service reliability. A portal is optional; a supported consumer outcome is the purpose.

[All career paths](README.md) · [Directory homepage](../README.md)

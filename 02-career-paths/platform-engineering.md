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

## Pick the workflow you need to support

| Consumer task | Relevant collection |
| --- | --- |
| Generate a service and a delivery path | [CI/CD](../03-topics/cicd.md) |
| Provision a supported environment | [Infrastructure as Code](../03-topics/infrastructure-as-code.md) |
| Deploy and reconcile applications | [GitOps](../03-topics/gitops.md) |
| Investigate the platform’s own failures | [Observability](../03-topics/observability.md) |

<table>
<tr>
<td align="center"><a href="../04-tools/github-actions.md"><img src="../assets/logos/githubactions.svg" width="48" height="48" alt="GitHub Actions"/><br/>GitHub Actions</a></td>
<td align="center"><a href="../04-tools/terraform.md"><img src="../assets/logos/terraform.svg" width="48" height="48" alt="Terraform"/><br/>Terraform</a></td>
<td align="center"><a href="../04-tools/argo-cd.md"><img src="../assets/logos/argo.svg" width="48" height="48" alt="Argo CD"/><br/>Argo CD</a></td>
<td align="center"><a href="../04-tools/kubernetes.md"><img src="../assets/logos/kubernetes.svg" width="48" height="48" alt="Kubernetes"/><br/>Kubernetes</a></td>
</tr>
</table>


## Try one consumer journey

Design onboarding for a small service. State what the user supplies, what gets created, who owns it, and how partial failure is reported. Prototype only the integrations you can safely support in an owned test environment. Remove generated repositories, infrastructure, and temporary credentials when finished.

[Explore projects →](../06-practice/projects.md)

Continue to [DevOps](devops.md) for delivery implementation or [SRE](sre.md) for shared-service reliability. A portal is optional; a supported consumer outcome is the purpose.

[All career paths](README.md) · [Directory homepage](../README.md)

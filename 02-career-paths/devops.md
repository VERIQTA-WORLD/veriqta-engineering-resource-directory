# DevOps Engineering

Follow a change from source code to a working service. Start with version control, a reproducible application, and a delivery workflow you can explain.

[Foundations](#make-the-basics-useful) · [Resources](#three-good-starting-resources) · [Practice](#build-one-delivery-path)

## Three good starting resources

**[Pro Git →](https://git-scm.com/book/en/v2)**  
Use Git Basics to understand commits, history, and remotes before moving into branching workflows.  
**Free online · Book · Beginner onward**

**[Docker Get Started →](https://docs.docker.com/get-started/)**  
Choose a guided application tutorial to connect images, containers, configuration, and a running application.  
**Free documentation · Tutorials · Check installation and account requirements**

**[DORA: Continuous delivery →](https://dora.dev/capabilities/continuous-delivery/)**  
Understand the practices behind releasing safely, including feedback, testing, security, and team dependencies.  
**Free · Engineering guide · Useful once you know a basic delivery workflow**

## Choose your next gap

If you can already package an application, go straight to a workflow. If your workflow succeeds but users still cannot reach the service, study the deployment and request path before adding more pipeline stages.

## Make the basics useful

[Linux](linux-systems.md) → [Networking](network-engineering.md) → [Git](https://git-scm.com/book/en/v2) → [Containers](https://docs.docker.com/get-started/) → [CI/CD](https://dora.dev/capabilities/continuous-delivery/)

Treat this as a starting route. If you already operate services, go directly to the subject behind your current problem.

## Tools along the delivery path

<table>
<tr>
<td align="center"><a href="https://git-scm.com/book/en/v2"><img src="../assets/logos/git.svg" width="48" height="48" alt="Git"/><br/>Git</a></td>
<td align="center"><a href="https://docs.docker.com/get-started/"><img src="../assets/logos/docker.svg" width="48" height="48" alt="Docker"/><br/>Docker</a></td>
<td align="center"><a href="https://docs.github.com/en/actions"><img src="../assets/logos/githubactions.svg" width="48" height="48" alt="GitHub Actions"/><br/>GitHub Actions</a></td>
<td align="center"><a href="https://developer.hashicorp.com/terraform/tutorials"><img src="../assets/logos/terraform.svg" width="48" height="48" alt="Terraform"/><br/>Terraform</a></td>
</tr>
</table>

Use the official references above for configuration details. For your first pipeline, the [GitHub Actions documentation](https://docs.github.com/en/actions) provides the workflow concepts and implementation reference; runner use and account features have separate conditions.

## Build one delivery path

Start with [GitHub’s example workflow](https://docs.github.com/en/actions/tutorials/create-an-example-workflow), then replace its demonstration command with a test for your application. You need a GitHub account and permission to edit workflows; check runner allowances before running it.

Keep one passing run and one deliberately failing test. Explain which commit ran, why the failure blocked progress, and how you corrected it. Add packaging with [Docker’s application tutorial](https://docs.docker.com/get-started/tutorials/run-an-app/) once that feedback loop works. A passing test is one piece of release evidence; verify a request against the running application too.

Delete exercise containers and unused workflow credentials. Keep the small repository if you want a portfolio example: its useful evidence is the failure and recovery, alongside the successful run.

When the main concern becomes dependable operation, continue to [SRE](sre.md). When several teams need a supported shared workflow, explore [platform engineering](platform-engineering.md).

[All career paths](README.md) · [Directory homepage](../README.md)

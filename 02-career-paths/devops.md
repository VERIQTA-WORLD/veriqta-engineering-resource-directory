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

## Make the basics useful

[Linux](../03-topics/linux.md) → [Networking](../03-topics/networking.md) → [Git](../04-tools/git.md) → [Containers](../03-topics/containers.md) → [CI/CD](../03-topics/cicd.md)

Treat this as a starting route. If you already operate services, go directly to the subject behind your current problem.

## Connect the tools

<table>
<tr>
<td align="center"><a href="../04-tools/git.md"><img src="../assets/logos/git.svg" width="48" height="48" alt="Git"/><br/>Git</a></td>
<td align="center"><a href="../04-tools/docker.md"><img src="../assets/logos/docker.svg" width="48" height="48" alt="Docker"/><br/>Docker</a></td>
<td align="center"><a href="../04-tools/github-actions.md"><img src="../assets/logos/githubactions.svg" width="48" height="48" alt="GitHub Actions"/><br/>GitHub Actions</a></td>
<td align="center"><a href="../04-tools/terraform.md"><img src="../assets/logos/terraform.svg" width="48" height="48" alt="Terraform"/><br/>Terraform</a></td>
</tr>
</table>


Use the tool pages for focused documentation and practice. For your first pipeline, the [GitHub Actions documentation](https://docs.github.com/en/actions) provides the workflow concepts and implementation reference; runner use and account features have separate conditions.

## Build one delivery path

Package a small application, track changes in Git, and add a workflow that checks it. Keep a functional request as evidence that the deployed application works. Use synthetic data, follow the selected tutorial’s prerequisites, and remove exercise containers, volumes, and test credentials afterward.

[Find projects →](../06-practice/projects.md) · [Explore pipeline failures →](../07-troubleshooting/pipelines.md)

When the main concern becomes dependable operation, continue to [SRE](sre.md). When several teams need a supported shared workflow, explore [platform engineering](platform-engineering.md).

[All career paths](README.md) · [Directory homepage](../README.md)

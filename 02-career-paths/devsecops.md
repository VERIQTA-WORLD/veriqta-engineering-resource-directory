# DevSecOps Engineering

Focus on how a change moves through source, build, artifact, deployment, and runtime boundaries. Choose resources that help you understand and verify the controls at those boundaries.

## Begin with the control you need

| Your question | Resource | Access and level |
| --- | --- | --- |
| Where does security fit in the delivery lifecycle? | [OWASP DevSecOps Guideline](https://owasp.org/projects/devsecops-guideline) — use its categories to locate relevant practices | Free · Intermediate |
| Can untrusted input reach a privileged job? | [GitHub Actions secure use](https://docs.github.com/en/actions/reference/security/secure-use) — inspect credentials, dependencies, and workflow execution | Free documentation · Workflow familiarity needed |
| What does artifact provenance establish? | [SLSA specification](https://slsa.dev/spec/) — study the selected version’s threats, tracks, and provenance | Free specification · Advanced |

Provenance helps explain origin and process. You still need other evidence to assess whether an artifact is appropriate to run.

## Follow the delivery boundary

<table>
<tr>
<td align="center"><a href="../04-tools/git.md"><img src="../assets/logos/git.svg" width="48" height="48" alt="Git"/><br/>Git</a></td>
<td align="center"><a href="../04-tools/github-actions.md"><img src="../assets/logos/githubactions.svg" width="48" height="48" alt="GitHub Actions"/><br/>GitHub Actions</a></td>
<td align="center"><a href="../04-tools/docker.md"><img src="../assets/logos/docker.svg" width="48" height="48" alt="Docker"/><br/>Docker</a></td>
<td align="center"><a href="../04-tools/kubernetes.md"><img src="../assets/logos/kubernetes.svg" width="48" height="48" alt="Kubernetes"/><br/>Kubernetes</a></td>
</tr>
</table>


| Boundary | Explore |
| --- | --- |
| Source and workflow changes | [Git](../04-tools/git.md) · [CI/CD](../03-topics/cicd.md) |
| Images and runtime configuration | [Containers](../03-topics/containers.md) · [Security](../03-topics/security.md) |
| Cluster deployment and workload access | [Kubernetes](../03-topics/kubernetes.md) |

## Review one test workflow

Use an owned disposable repository and synthetic inputs. Identify triggers, permissions, secrets, dependencies, and deployment authority. Test a rejected input or denied operation alongside the expected successful path. Revoke test credentials and remove unused integrations afterward.

[Find challenges →](../06-practice/challenges.md)

Use [DevOps](devops.md) for delivery fundamentals and [cloud security](cloud-security.md) for provider access and resource protection. A scanner is one control; it does not define the whole practice.

[All career paths](README.md) · [Directory homepage](../README.md)

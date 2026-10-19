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
<td align="center"><a href="https://git-scm.com/book/en/v2"><img src="../assets/logos/git.svg" width="48" height="48" alt="Git"/><br/>Git</a></td>
<td align="center"><a href="https://docs.github.com/en/actions"><img src="../assets/logos/githubactions.svg" width="48" height="48" alt="GitHub Actions"/><br/>GitHub Actions</a></td>
<td align="center"><a href="https://docs.docker.com/get-started/"><img src="../assets/logos/docker.svg" width="48" height="48" alt="Docker"/><br/>Docker</a></td>
<td align="center"><a href="https://kubernetes.io/docs/concepts/overview/"><img src="../assets/logos/kubernetes.svg" width="48" height="48" alt="Kubernetes"/><br/>Kubernetes</a></td>
</tr>
</table>

| Boundary | Explore |
| --- | --- |
| Source and workflow changes | [Git](https://git-scm.com/book/en/v2) · [CI/CD](https://dora.dev/capabilities/continuous-delivery/) |
| Images and runtime configuration | [Containers](https://docs.docker.com/get-started/) · [Security](devsecops.md) |
| Cluster deployment and workload access | [Kubernetes](kubernetes-engineering.md) |

## Review a workflow’s trust boundaries

Create a small workflow using [GitHub’s example](https://docs.github.com/en/actions/tutorials/create-an-example-workflow). With the [secure use reference](https://docs.github.com/en/actions/reference/security/secure-use) beside it, trace who can supply input, where that input is used, and which jobs hold authority. You need repository administration permissions for some settings; runner and account conditions apply.

Produce a short before-and-after review: the risk, the change, and the evidence that ordinary work still succeeds. Start with token permissions and third-party action dependencies. Keep secrets out of the exercise and remove temporary integrations afterward.

Once that review is clear, use the SLSA specification above to examine what evidence your build produces about its origin. A successful security scan does not answer that question.

Use [DevOps](devops.md) for delivery fundamentals and [cloud security](cloud-security.md) for provider access and resource protection. A scanner is one control; it does not define the whole practice.

[All career paths](README.md) · [Directory homepage](../README.md)

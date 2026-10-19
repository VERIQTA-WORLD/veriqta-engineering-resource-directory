# GitOps and Reconciliation

Read resources that distinguish configuration in Git from the state a controller actually observes.

## Follow desired state into a running system

| Open | What you can find | Access |
| --- | --- | --- |
| [OpenGitOps principles](https://opengitops.dev/) | Read the principles before treating any particular controller as the definition of GitOps. | Free principles and project material |
| [CNCF online programs](https://www.cncf.io/online-programs/) | Browse project and practitioner sessions; choose a recording about your current cloud-native question. | Event catalog; session access varies |
| [Kubernetes in Action, Second Edition](https://www.manning.com/books/kubernetes-in-action-second-edition) | Marko Lukša and Kevin Conner; use the contents to select the workload or cluster subject you need. | Paid book; publisher samples |

## Focused references

**[Argo CD getting started →](https://argo-cd.readthedocs.io/en/stable/getting_started/)**  
Follow a first application and connect Git configuration with synchronization state.  
**Free guide; cluster access required**

**[Flux getting started →](https://fluxcd.io/flux/get-started/)**  
Inspect the bootstrap flow and the source and reconciliation resources it creates.  
**Free guide; repository and cluster access required**

## Follow the tools

[Argo CD](../04-tools-and-technologies/argo-cd.md) · [Flux](../04-tools-and-technologies/flux.md) · [Kustomize](../04-tools-and-technologies/kustomize.md) · [Helm](../04-tools-and-technologies/helm.md)

## Put one idea to work

Change a learning application’s Git configuration and explain its reconciliation status before and after synchronization. Use the selected guide’s prerequisites and verification steps. Choose an owned or provided learning environment, keep sensitive data out of your notes, and remove the exercise resources when finished.

[Browse this collection](README.md) · [Directory homepage](../README.md)

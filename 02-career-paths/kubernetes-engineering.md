# Kubernetes Engineering

If you can already run and explain a containerized application, use this page to find resources for orchestration, workload configuration, and cluster troubleshooting. Otherwise, begin with [Docker](../04-tools/docker.md).

<table>
<tr>
<td align="center"><a href="../04-tools/kubernetes.md"><img src="../assets/logos/kubernetes.svg" width="48" height="48" alt="Kubernetes"/><br/>Kubernetes</a></td>
<td align="center"><a href="../04-tools/helm.md"><img src="../assets/logos/helm.svg" width="48" height="48" alt="Helm"/><br/>Helm</a></td>
<td align="center"><a href="../04-tools/argo-cd.md"><img src="../assets/logos/argo.svg" width="48" height="48" alt="Argo CD"/><br/>Argo CD</a></td>
</tr>
</table>


## Choose the reference for your task

**[Learn Kubernetes Basics →](https://kubernetes.io/docs/tutorials/kubernetes-basics/)**  
Follow the introductory route through deploying, exposing, scaling, and updating an application.  
**Free tutorials · Foundation · Check the exercise environment**

**[Kubernetes concepts →](https://kubernetes.io/docs/concepts/overview/)**  
Build the model behind the objects and controllers you use; follow the concept relevant to your workload.  
**Free documentation · Foundation to intermediate**

**[Troubleshooting applications →](https://kubernetes.io/docs/tasks/debug/debug-application/)**  
Select the diagnostic guide matching a failing workload or application boundary.  
**Free documentation · Intermediate · Appropriate cluster access required**

Use documentation matching your cluster release. Public documentation does not imply free cluster infrastructure.

## Connect the surrounding knowledge

[Containers](../03-topics/containers.md) · [Networking](../03-topics/networking.md) · [Security](../03-topics/security.md) · [Observability](../03-topics/observability.md)

Use [Helm](../04-tools/helm.md) for packaging resources and [Argo CD](../04-tools/argo-cd.md) when your task involves Git-controlled reconciliation. Learn the workload model before adding either.

## Build and investigate

Deploy a small synthetic application in a disposable cluster. Verify a request through its Service, change one configuration value, and investigate the result. Keep expected behavior and actual observations separate. Remove the cluster and check separately for any external storage, load balancers, registry artifacts, or credentials created during the exercise.

[Find labs →](../06-practice/labs.md) · [Kubernetes troubleshooting →](../07-troubleshooting/kubernetes.md) · [Certification resources →](../08-learning/certifications.md)

Continue to [platform engineering](platform-engineering.md) for shared developer capabilities or [SRE](sre.md) for service objectives and operating decisions.

[All career paths](README.md) · [Directory homepage](../README.md)

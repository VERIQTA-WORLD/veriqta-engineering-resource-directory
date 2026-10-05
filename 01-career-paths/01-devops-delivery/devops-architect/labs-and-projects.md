# Labs, workshops, and implementation examples

Linked practice resources for exploring design choices in a sandbox. These are external exercises and examples, not VERIQTA-tested production deployments.

Before running an exercise, read its current prerequisites, permissions, resource list, expected results, and cleanup instructions. Use disposable accounts or environments, protect credentials, set spending controls where available, and confirm removal of storage and supporting services. Never run destructive or failure-injection experiments against an unauthorized target.

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

## Cloud architecture workshops and deployment samples

Read the individual exercise before deployment. Documentation access does not imply free compute, storage, network traffic, or managed services.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [AWS Workshops](https://workshops.aws/) | Find workshops for architecture, security, networking, operations, and delivery topics. | Intermediate; prerequisites, regional support, and AWS charges vary by workshop. Follow its cleanup instructions. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Intermediate; use a sandbox account and review resource creation and removal per lab. |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. |
| [AKS baseline implementation](https://github.com/mspnp/aks-baseline) | Inspect the infrastructure sample accompanying the AKS baseline architecture. | Advanced; review the repository's current instructions and required Azure resources before deploying. |
| [Google Cloud example foundation](https://github.com/terraform-google-modules/terraform-example-foundation) | Inspect infrastructure code for enterprise foundation patterns. | Advanced; substantial organization, permission, and billing prerequisites. Treat as a reference implementation, not a starter lab. |

## Local and project-maintained practice resources

Prefer disposable local environments for early experiments. Local clusters still use machine resources and do not reproduce every production boundary.

| Resource | What it helps you do | Level and selection notes |
| --- | --- | --- |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Foundation to intermediate; driver and operating-system prerequisites vary. |
| [Argo CD example applications](https://github.com/argoproj/argocd-example-apps) | Inspect example applications for GitOps demonstrations. | Intermediate; review manifests and controller versions. Examples are not hardened production configurations. |
| [Flux getting started](https://fluxcd.io/flux/get-started/) | Practice GitOps bootstrap and reconciliation using project guidance. | Intermediate; requires a cluster and repository access. Review credentials and generated repository changes. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. |
| [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/) | Practice basic metrics collection and querying. | Foundation to intermediate; a starter setup does not establish monitoring availability or retention design. |
| [Backstage getting started](https://backstage.io/docs/getting-started/) | Explore a developer portal and its application structure. | Intermediate; requires the documented development environment. Review dependency and authentication guidance. |
| [Running k6](https://grafana.com/docs/k6/latest/get-started/running-k6/) | Learn how to create and interpret initial load tests. | Intermediate; test only systems you own or are authorized to test. Start with controlled targets. |

---

[Folder overview](README.md) · [Tools](toolkit.md) · [Documentation](official-documentation.md) · [Architecture](reference-architectures.md) · [Learning](learning-resources.md) · [Practice](labs-and-projects.md) · [Operations](production-responsibilities.md) · [Standards](standards-and-frameworks.md) · [Related careers](related-careers.md)

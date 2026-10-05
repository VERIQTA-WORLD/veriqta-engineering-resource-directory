# DevOps consultant: labs, examples, and projects

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Provider workshops for assessment prototypes

Use temporary client-approved environments. Record assumptions, estimated charges, controls tested, and the cleanup owner before deploying. A workshop is not a hardened production design.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Workshops](https://workshops.aws/) | Find workshops for architecture, security, networking, operations, and delivery topics. | Public reference. Intermediate; prerequisites, regional support, and AWS charges vary by workshop. Follow its cleanup instructions. Practice and cleanup: Choose a specific workshop and read its cleanup section before starting. Inspect compute, networking, storage, identities, and managed services left in the account. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Public reference. Intermediate; use a sandbox account and review resource creation and removal per lab. Practice and cleanup: Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Public reference. Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. Practice and cleanup: Read the workshop’s cleanup guidance and inspect cluster-related storage, networking, IAM, and managed services rather than removing only workloads. |
| [AKS baseline implementation](https://github.com/mspnp/aks-baseline) | Inspect the infrastructure sample accompanying the AKS baseline architecture. | Public reference. Advanced; review the repository's current instructions and required Azure resources before deploying. Practice and cleanup: Use the sample repository’s documented deployment and resource-removal guidance. Review Azure resources, retained data, identities, and shared dependencies before deletion. |
| [Google Cloud example foundation](https://github.com/terraform-google-modules/terraform-example-foundation) | Inspect infrastructure code for enterprise foundation patterns. | Public reference. Advanced; substantial organization, permission, and billing prerequisites. Treat as a reference implementation, not a starter lab. Practice and cleanup: This is an organization-level reference implementation. Review the repository’s destruction caveats and shared dependencies; agree what must remain before removing infrastructure. |

## Platform and delivery demonstrations

Use small demonstrators to evaluate an interface, promotion model, or developer workflow. Document the features not tested before drawing conclusions.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Public reference. Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. Practice and cleanup: Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Public reference. Foundation to intermediate; driver and operating-system prerequisites vary. Practice and cleanup: Use the start guide’s cluster lifecycle instructions. Review driver-managed machines, volumes, and any external resources before declaring cleanup complete. |
| [Argo CD example applications](https://github.com/argoproj/argocd-example-apps) | Inspect example applications for GitOps demonstrations. | Public reference. Intermediate; review manifests and controller versions. Examples are not hardened production configurations. Practice and cleanup: Inspect each application before synchronization. Remove its deployed resources through the owning controller or documented project workflow, then inspect persistent data and external services. |
| [Flux getting started](https://fluxcd.io/flux/get-started/) | Practice GitOps bootstrap and reconciliation using project guidance. | Public reference. Intermediate; requires a cluster and repository access. Review credentials and generated repository changes. Practice and cleanup: Review the guide’s bootstrap and controller setup. Remove test reconciliation resources and controllers deliberately; inspect repository changes and external resources separately. |
| [Backstage getting started](https://backstage.io/docs/getting-started/) | Explore a developer portal and its application structure. | Public reference. Intermediate; requires the documented development environment. Review dependency and authentication guidance. Practice and cleanup: Stop the test application and remove unneeded local dependencies and data. Review any external identities, repositories, or resources created through integrations. |

## Measurement and infrastructure validation

Use these to demonstrate telemetry, load behavior, drift review, or infrastructure testing. Keep data and target systems within the approved engagement boundary.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Public reference. Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. Practice and cleanup: Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |
| [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/) | Practice basic metrics collection and querying. | Public reference. Foundation to intermediate; a starter setup does not establish monitoring availability or retention design. Practice and cleanup: Stop the local practice server when finished and remove unneeded test configuration and data after reviewing any evidence you intend to keep. |
| [Running k6](https://grafana.com/docs/k6/latest/get-started/running-k6/) | Learn how to create and interpret initial load tests. | Public reference. Intermediate; test only systems you own or are authorized to test. Start with controlled targets. Practice and cleanup: Run only against authorized targets. Stop the test, remove disposable targets, and review retained result files and any hosted-test usage separately. |
| [Terraform testing tutorial](https://developer.hashicorp.com/terraform/tutorials/configuration-language/test) | Practice assertions and test setup for infrastructure configuration. | Intermediate; public tutorial. Tests may provision infrastructure; inspect run modes, permissions, and teardown before execution. Practice and cleanup: Inspect the test run mode and generated resources. The tutorial explains ephemeral test infrastructure; investigate resources retained after interrupted or failed tests. |
| [Terraform refresh-only planning tutorial](https://developer.hashicorp.com/terraform/tutorials/state/refresh) | Practice examining infrastructure drift through the provider's state-refresh tutorial. | Intermediate; public tutorial. Example provisioning needs cloud credentials and can incur charges; follow the tutorial's destruction instructions. Practice and cleanup: Use the tutorial’s Clean up resources section; verify infrastructure removal before discarding its state and local workspace. |
| [Pulumi testing guide](https://www.pulumi.com/docs/iac/guides/testing/) | Compare unit, property, and integration approaches for infrastructure expressed as code. | Intermediate; public guide. Provider integration tests can create billable resources and require cleanup. Practice and cleanup: The guide distinguishes mocked unit tests from deployed integration tests. Verify ephemeral-resource destruction and inspect failed-test leftovers. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

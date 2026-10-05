# Platform reliability engineer: labs, examples, and projects

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

## Browse this page

- [Disposable platform environments](#disposable-platform-environments)
- [Telemetry, policy, and reconciliation practice](#telemetry-policy-and-reconciliation-practice)
- [Provider reference implementations](#provider-reference-implementations)

## Disposable platform environments

Use local clusters and reference applications to observe platform failure and recovery. Inspect persistent data and any external resources before teardown.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. | Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Foundation to intermediate; driver and operating-system prerequisites vary. | Use the start guide’s cluster lifecycle instructions. Review driver-managed machines, volumes, and any external resources before declaring cleanup complete. |
| [Backstage getting started](https://backstage.io/docs/getting-started/) | Explore a developer portal and its application structure. | Intermediate; requires the documented development environment. Review dependency and authentication guidance. | Stop the test application and remove unneeded local dependencies and data. Review any external identities, repositories, or resources created through integrations. |
| [Backstage software templates](https://backstage.io/docs/features/software-templates/) | Design scaffolding interfaces for repeatable developer workflows. | Intermediate; public project documentation. Template actions execute with configured credentials; validate inputs and review privileged integrations. | Templates can publish repositories or invoke external actions. Inspect the selected action’s effects and remove its created test resources separately from stopping Backstage. |
| [Crossplane getting started](https://docs.crossplane.io/latest/get-started/) | Find project-maintained introductory control-plane examples and setup guidance. | Intermediate to advanced; public tutorial navigation. Providers can create external resources; confirm deletion behavior and clean those resources before removing the control plane. | Read the chosen provider and deletion-policy guidance. Verify removal or intentional retention of managed external resources before removing controllers or the practice cluster. |
| [Argo CD example applications](https://github.com/argoproj/argocd-example-apps) | Inspect example applications for GitOps demonstrations. | Intermediate; review manifests and controller versions. Examples are not hardened production configurations. | Inspect each application before synchronization. Remove its deployed resources through the owning controller or documented project workflow, then inspect persistent data and external services. |
| [Flux getting started](https://fluxcd.io/flux/get-started/) | Practice GitOps bootstrap and reconciliation using project guidance. | Intermediate; requires a cluster and repository access. Review credentials and generated repository changes. | Review the guide’s bootstrap and controller setup. Remove test reconciliation resources and controllers deliberately; inspect repository changes and external resources separately. |

## Telemetry, policy, and reconciliation practice

Build a small platform experiment with explicit expectations: a user action, a failure condition, observable impact, and recovery evidence.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. | Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |
| [kube-prometheus](https://github.com/prometheus-operator/kube-prometheus) | Study manifests and dashboards for a Kubernetes monitoring stack. | Advanced; public implementation repository. Match supported Kubernetes versions and review resource use; remove the stack's resources when a practice cluster is retired. | Use the repository’s setup and teardown documentation for the selected release. Review persistent telemetry storage and cluster resources before retiring the environment. |
| [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/) | Practice basic metrics collection and querying. | Foundation to intermediate; a starter setup does not establish monitoring availability or retention design. | Stop the local practice server when finished and remove unneeded test configuration and data after reviewing any evidence you intend to keep. |
| [Terraform testing tutorial](https://developer.hashicorp.com/terraform/tutorials/configuration-language/test) | Practice assertions and test setup for infrastructure configuration. | Intermediate; public tutorial. Tests may provision infrastructure; inspect run modes, permissions, and teardown before execution. | Inspect the test run mode and generated resources. The tutorial explains ephemeral test infrastructure; investigate resources retained after interrupted or failed tests. |
| [Pulumi testing guide](https://www.pulumi.com/docs/iac/guides/testing/) | Compare unit, property, and integration approaches for infrastructure expressed as code. | Intermediate; public guide. Provider integration tests can create billable resources and require cleanup. | The guide distinguishes mocked unit tests from deployed integration tests. Verify ephemeral-resource destruction and inspect failed-test leftovers. |
| [Ansible Molecule](https://docs.ansible.com/projects/molecule/) | Evaluate scenarios for developing and testing Ansible collections, playbooks, and roles. | Intermediate; public documentation. Scenario drivers and targets determine infrastructure, privileges, and cleanup requirements. | Review the scenario create, converge, verify, and destroy playbooks. Confirm destruction of its actual target resources and any external dependencies. |

## Provider reference implementations

Choose one environment with an account and cost boundary. These resources include different scopes; read the selected deployment and removal instructions first.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. | Read the workshop’s cleanup guidance and inspect cluster-related storage, networking, IAM, and managed services rather than removing only workloads. |
| [AKS baseline implementation](https://github.com/mspnp/aks-baseline) | Inspect the infrastructure sample accompanying the AKS baseline architecture. | Advanced; review the repository's current instructions and required Azure resources before deploying. | Use the sample repository’s documented deployment and resource-removal guidance. Review Azure resources, retained data, identities, and shared dependencies before deletion. |
| [Google Cloud example foundation](https://github.com/terraform-google-modules/terraform-example-foundation) | Inspect infrastructure code for enterprise foundation patterns. | Advanced; substantial organization, permission, and billing prerequisites. Treat as a reference implementation, not a starter lab. | This is an organization-level reference implementation. Review the repository’s destruction caveats and shared dependencies; agree what must remain before removing infrastructure. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Intermediate; use a sandbox account and review resource creation and removal per lab. | Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |
| [AWS Workshops](https://workshops.aws/) | Find workshops for architecture, security, networking, operations, and delivery topics. | Intermediate; prerequisites, regional support, and AWS charges vary by workshop. Follow its cleanup instructions. | Choose a specific workshop and read its cleanup section before starting. Inspect compute, networking, storage, identities, and managed services left in the account. |

## Use the linked practice material

Choose the upstream exercise or example that matches your question and version. Before starting, identify the test environment, permissions, target scope, expected observation, stop condition, and resources it can create. Keep enough configuration and result evidence to explain what happened; do not keep credentials or sensitive production data in a public project.

If the expected result does not appear, use the source's diagnostic guidance to check prerequisites, versions, permissions, target selection, connectivity, and observation points. Cleanup is a separate verification: confirm fault removal and resource retirement, including retained storage and resources created outside the local environment. These links were reviewed as resources; the exercises were not executed for this directory.

[Browse the other collections](README.md#resource-collections)

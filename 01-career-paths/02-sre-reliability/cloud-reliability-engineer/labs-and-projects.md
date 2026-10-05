# Cloud reliability engineer: labs, examples, and projects

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

## Browse this page

- [Provider workload and foundation exercises](#provider-workload-and-foundation-exercises)
- [Cloud failure and recovery practice](#cloud-failure-and-recovery-practice)
- [Workload telemetry and deployment practice](#workload-telemetry-and-deployment-practice)

## Provider workload and foundation exercises

Choose a specific exercise and read its IAM, billing, dependency, and teardown requirements before provisioning.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [AWS Workshops](https://workshops.aws/) | Find workshops for architecture, security, networking, operations, and delivery topics. | Intermediate; prerequisites, regional support, and AWS charges vary by workshop. Follow its cleanup instructions. | Choose a specific workshop and read its cleanup section before starting. Inspect compute, networking, storage, identities, and managed services left in the account. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Intermediate; use a sandbox account and review resource creation and removal per lab. | Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. | Read the workshop’s cleanup guidance and inspect cluster-related storage, networking, IAM, and managed services rather than removing only workloads. |
| [AKS baseline implementation](https://github.com/mspnp/aks-baseline) | Inspect the infrastructure sample accompanying the AKS baseline architecture. | Advanced; review the repository's current instructions and required Azure resources before deploying. | Use the sample repository’s documented deployment and resource-removal guidance. Review Azure resources, retained data, identities, and shared dependencies before deletion. |
| [Google Cloud example foundation](https://github.com/terraform-google-modules/terraform-example-foundation) | Inspect infrastructure code for enterprise foundation patterns. | Advanced; substantial organization, permission, and billing prerequisites. Treat as a reference implementation, not a starter lab. | This is an organization-level reference implementation. Review the repository’s destruction caveats and shared dependencies; agree what must remain before removing infrastructure. |

## Cloud failure and recovery practice

Use controlled experiment targets, stop conditions, and isolated data. Validate both residual fault removal and useful service recovery.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [AWS FIS tutorial: instance stop and start](https://docs.aws.amazon.com/fis/latest/userguide/fis-tutorial-stop-instances.html) | Create an experiment that stops and restarts two test EC2 instances, then verify the observed instance transitions. | Intermediate; public cloud tutorial. Requires test instances, experiment permissions, and an account; compute and service use can incur charges. | Requires two test EC2 instances, an experiment role, and AWS FIS access. Keep instance-state and experiment evidence. Follow Step 5: Clean up for instances and the template, then inspect retained disks and identities; resource use can incur charges. |
| [Azure Chaos Studio Workspaces documentation (preview)](https://learn.microsoft.com/en-us/azure/chaos-studio/) | Evaluate Azure fault experiments and service-specific target requirements. | Intermediate to advanced; public documentation for a preview service. Check feature scope, supported targets, account requirements, and preview limitations before planning an experiment. | This is preview Workspaces documentation, with separate classic experiment references. Choose the correct quickstart and resource model first; check supported targets, permissions, cost, abort behavior, and removal of scenarios, faults, and test resources. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. | This is a restore command reference, not a complete prebuilt lab. Requires a valid backup repository, matching database tools, permissions, and a separate restore target. Verify recovered data and recovery-point evidence; retire only test targets and never delete the source backup as routine cleanup. |
| [Terraform testing tutorial](https://developer.hashicorp.com/terraform/tutorials/configuration-language/test) | Practice assertions and test setup for infrastructure configuration. | Intermediate; public tutorial. Tests may provision infrastructure; inspect run modes, permissions, and teardown before execution. | Inspect the test run mode and generated resources. The tutorial explains ephemeral test infrastructure; investigate resources retained after interrupted or failed tests. |
| [Terraform refresh-only planning tutorial](https://developer.hashicorp.com/terraform/tutorials/state/refresh) | Practice examining infrastructure drift through the provider's state-refresh tutorial. | Intermediate; public tutorial. Example provisioning needs cloud credentials and can incur charges; follow the tutorial's destruction instructions. | Use the tutorial’s Clean up resources section; verify infrastructure removal before discarding its state and local workspace. |

## Workload telemetry and deployment practice

Use local or sandbox deployments to observe the control path and application behavior. Remove retained storage and external resources after the exercise.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. | Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Foundation to intermediate; driver and operating-system prerequisites vary. | Use the start guide’s cluster lifecycle instructions. Review driver-managed machines, volumes, and any external resources before declaring cleanup complete. |
| [Flux getting started](https://fluxcd.io/flux/get-started/) | Practice GitOps bootstrap and reconciliation using project guidance. | Intermediate; requires a cluster and repository access. Review credentials and generated repository changes. | Review the guide’s bootstrap and controller setup. Remove test reconciliation resources and controllers deliberately; inspect repository changes and external resources separately. |
| [Argo CD example applications](https://github.com/argoproj/argocd-example-apps) | Inspect example applications for GitOps demonstrations. | Intermediate; review manifests and controller versions. Examples are not hardened production configurations. | Inspect each application before synchronization. Remove its deployed resources through the owning controller or documented project workflow, then inspect persistent data and external services. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. | Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |
| [Running k6](https://grafana.com/docs/k6/latest/get-started/running-k6/) | Learn how to create and interpret initial load tests. | Intermediate; test only systems you own or are authorized to test. Start with controlled targets. | Run only against authorized targets. Stop the test, remove disposable targets, and review retained result files and any hosted-test usage separately. |

## Use the linked practice material

Choose the upstream exercise or example that matches your question and version. Before starting, identify the test environment, permissions, target scope, expected observation, stop condition, and resources it can create. Keep enough configuration and result evidence to explain what happened; do not keep credentials or sensitive production data in a public project.

If the expected result does not appear, use the source's diagnostic guidance to check prerequisites, versions, permissions, target selection, connectivity, and observation points. Cleanup is a separate verification: confirm fault removal and resource retirement, including retained storage and resources created outside the local environment. These links were reviewed as resources; the exercises were not executed for this directory.

[Browse the other collections](README.md#resource-collections)

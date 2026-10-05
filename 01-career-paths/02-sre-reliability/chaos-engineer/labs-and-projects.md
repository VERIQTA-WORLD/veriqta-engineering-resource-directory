# Chaos engineer: labs, examples, and projects

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

## Browse this page

- [Local fault experiments](#local-fault-experiments)
- [Cluster experiments and observation](#cluster-experiments-and-observation)
- [Cloud experiments and recovery evidence](#cloud-experiments-and-recovery-evidence)

## Local fault experiments

Use a disposable dependency and a documented fault-control interface. Verify removal of the fault and recovery of useful service behavior before deleting the environment.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [Toxiproxy usage and API examples](https://github.com/Shopify/toxiproxy/blob/main/README.md) | Inspect proxy configuration and fault-control examples before writing a dependency-failure test. | Intermediate; public project examples. Reset faults and remove the disposable proxy; never intercept unrelated traffic. | Requires a Toxiproxy server, a client, and a disposable application dependency. Use the README API and toxic examples; retain the baseline, fault, and recovery results, then remove toxics/proxies and stop the server. |
| [Chaos Toolkit documentation](https://chaostoolkit.org/) | Explore experiment definitions, drivers, and execution guidance for hypothesis-based failure testing. | Advanced; public project documentation. Extensions need separate review; experiments can affect availability and data. | Requires the toolkit, relevant extensions, and authorized disposable targets. Read experiment, steady-state, journal, and rollback guidance; retain the journal and recovery evidence, then verify every injected effect and target resource is removed. |
| [stress-ng](https://github.com/ColinIanKing/stress-ng) | Explore controlled resource stressors for testing host and workload behavior. | Advanced; public project repository. Stressors can destabilize a host; use disposable environments and stop all stress processes afterward. | Requires a disposable host and a bounded stressor selection. Read the project warnings: privileged or excessive stress can destabilize the host. Capture the targeted resource and recovery evidence; stop every stressor and remove designated temporary artifacts. |
| [Locust quick start](https://docs.locust.io/en/stable/quickstart.html) | Practice a Python-defined load test using project-maintained setup instructions. | Intermediate; public quick-start guide. The stable URL currently serves a development build; select documentation matching the installed Locust version and use authorized targets. | Requires Python, Locust, and an authorized target. Keep task definitions, observed request rate, errors, and generator limits; stop workers and remove the disposable target and data. |
| [Running k6](https://grafana.com/docs/k6/latest/get-started/running-k6/) | Learn how to create and interpret initial load tests. | Intermediate; test only systems you own or are authorized to test. Start with controlled targets. | Run only against authorized targets. Stop the test, remove disposable targets, and review retained result files and any hosted-test usage separately. |

## Cluster experiments and observation

Use a dedicated cluster and explicit test namespaces or targets. Inspect privileged components and remove experiments, controllers, and retained storage after the exercise.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [Install Chaos Mesh using Helm](https://chaos-mesh.org/docs/production-installation-using-helm/) | Install the experiment controllers in a Kubernetes environment and verify the deployment before selecting a fault experiment. | Intermediate; public installation guide. Requires a cluster and Helm; use a disposable practice cluster before considering production targets. | Requires Helm and a disposable Kubernetes cluster with a supported runtime. Use the installation verification and Uninstall Chaos Mesh sections; inspect remaining experiment resources, namespaces, permissions, and persistent storage after removal. |
| [LitmusChaos documentation](https://docs.litmuschaos.io/) | Review experiment and workflow guidance for resilience testing. | Advanced; public documentation. Inspect experiment privileges, target selection, cleanup, and recovery checks. | This is a documentation collection; choose a specific Litmus installation and experiment before execution. Check cluster access, target selectors, probes, permissions, and experiment cleanup; verify recovery and remove practice controllers and storage. |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. | Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Foundation to intermediate; driver and operating-system prerequisites vary. | Use the start guide’s cluster lifecycle instructions. Review driver-managed machines, volumes, and any external resources before declaring cleanup complete. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. | Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |
| [kube-prometheus](https://github.com/prometheus-operator/kube-prometheus) | Study manifests and dashboards for a Kubernetes monitoring stack. | Advanced; public implementation repository. Match supported Kubernetes versions and review resource use; remove the stack's resources when a practice cluster is retired. | Use the repository’s setup and teardown documentation for the selected release. Review persistent telemetry storage and cluster resources before retiring the environment. |

## Cloud experiments and recovery evidence

Use provider-approved experiment controls and a sandbox boundary. Cost, target permissions, stop conditions, and recovery steps belong in the test plan.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [AWS FIS tutorial: instance stop and start](https://docs.aws.amazon.com/fis/latest/userguide/fis-tutorial-stop-instances.html) | Create an experiment that stops and restarts two test EC2 instances, then verify the observed instance transitions. | Intermediate; public cloud tutorial. Requires test instances, experiment permissions, and an account; compute and service use can incur charges. | Requires two test EC2 instances, an experiment role, and AWS FIS access. Keep instance-state and experiment evidence. Follow Step 5: Clean up for instances and the template, then inspect retained disks and identities; resource use can incur charges. |
| [Azure Chaos Studio Workspaces documentation (preview)](https://learn.microsoft.com/en-us/azure/chaos-studio/) | Evaluate Azure fault experiments and service-specific target requirements. | Intermediate to advanced; public documentation for a preview service. Check feature scope, supported targets, account requirements, and preview limitations before planning an experiment. | This is preview Workspaces documentation, with separate classic experiment references. Choose the correct quickstart and resource model first; check supported targets, permissions, cost, abort behavior, and removal of scenarios, faults, and test resources. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Intermediate; use a sandbox account and review resource creation and removal per lab. | Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. | Read the workshop’s cleanup guidance and inspect cluster-related storage, networking, IAM, and managed services rather than removing only workloads. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. | This is a restore command reference, not a complete prebuilt lab. Requires a valid backup repository, matching database tools, permissions, and a separate restore target. Verify recovered data and recovery-point evidence; retire only test targets and never delete the source backup as routine cleanup. |

## Use the linked practice material

Choose the upstream exercise or example that matches your question and version. Before starting, identify the test environment, permissions, target scope, expected observation, stop condition, and resources it can create. Keep enough configuration and result evidence to explain what happened; do not keep credentials or sensitive production data in a public project.

If the expected result does not appear, use the source's diagnostic guidance to check prerequisites, versions, permissions, target selection, connectivity, and observation points. Cleanup is a separate verification: confirm fault removal and resource retirement, including retained storage and resources created outside the local environment. These links were reviewed as resources; the exercises were not executed for this directory.

[Browse the other collections](README.md#resource-collections)

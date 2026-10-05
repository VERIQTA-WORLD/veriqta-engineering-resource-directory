# Infrastructure reliability engineer: labs, examples, and projects

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

## Browse this page

- [Disposable hosts and configuration tests](#disposable-hosts-and-configuration-tests)
- [Resource and node experiments](#resource-and-node-experiments)
- [Monitoring and recovery demonstrations](#monitoring-and-recovery-demonstrations)

## Disposable hosts and configuration tests

Inspect target inventory, privileged initialization, test drivers, and cleanup before use. Retire generated machines, images, and storage after practice.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [Vagrant getting-started tutorials](https://developer.hashicorp.com/vagrant/tutorials/getting-started) | Practice a local machine lifecycle, provisioning, and destruction using the provider's tutorials. | Foundation; public tutorials. Downloaded boxes and provisioners need review; destroy machines and clean retained artifacts as appropriate. | Follow the machine lifecycle and destruction tutorial in this collection. Review retained boxes, host files, and downloaded artifacts separately. |
| [cloud-init YAML examples](https://cloudinit.readthedocs.io/en/latest/reference/examples.html) | Inspect initialization examples before writing machine bootstrap configuration. | Intermediate; public examples. User data can run privileged commands; test on disposable instances and remove the instances afterward. | These are privileged initialization examples, not standalone safe labs. Use disposable instances; remove the instances and retained disks or images through the provider. |
| [Ansible example playbooks](https://github.com/ansible/ansible-examples) | Inspect project-maintained examples of application configuration and orchestration. | Intermediate; public example repository. Check age, target assumptions, and credentials; adapt in disposable systems rather than treating examples as production defaults. | Review the selected playbook and target inventory first. Configuration changes do not automatically undo themselves; use disposable targets and retire them afterward. |
| [Ansible Molecule](https://docs.ansible.com/projects/molecule/) | Evaluate scenarios for developing and testing Ansible collections, playbooks, and roles. | Intermediate; public documentation. Scenario drivers and targets determine infrastructure, privileges, and cleanup requirements. | Review the scenario create, converge, verify, and destroy playbooks. Confirm destruction of its actual target resources and any external dependencies. |
| [Terraform testing tutorial](https://developer.hashicorp.com/terraform/tutorials/configuration-language/test) | Practice assertions and test setup for infrastructure configuration. | Intermediate; public tutorial. Tests may provision infrastructure; inspect run modes, permissions, and teardown before execution. | Inspect the test run mode and generated resources. The tutorial explains ephemeral test infrastructure; investigate resources retained after interrupted or failed tests. |
| [Terraform refresh-only planning tutorial](https://developer.hashicorp.com/terraform/tutorials/state/refresh) | Practice examining infrastructure drift through the provider's state-refresh tutorial. | Intermediate; public tutorial. Example provisioning needs cloud credentials and can incur charges; follow the tutorial's destruction instructions. | Use the tutorial’s Clean up resources section; verify infrastructure removal before discarding its state and local workspace. |
| [Packer tutorials](https://developer.hashicorp.com/packer/tutorials) | Find image-building walkthroughs and provider-specific examples. | Intermediate; public tutorial collection. Image builds require supported builders, credentials, compute, and removal of retained images. | Select a builder-specific tutorial before execution. Retire temporary build machines, retained images, snapshots, and storage according to that tutorial and provider. |

## Resource and node experiments

Use authorized, disposable targets for stress, I/O, and network tests. Stop generators, reset faults, and verify useful workload recovery.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. | Requires fio and carefully isolated test files or devices. Record the job definition, target, latency, throughput, and errors. Raw-device jobs can destroy data; stop jobs and remove only the designated test files. |
| [stress-ng](https://github.com/ColinIanKing/stress-ng) | Explore controlled resource stressors for testing host and workload behavior. | Advanced; public project repository. Stressors can destabilize a host; use disposable environments and stop all stress processes afterward. | Requires a disposable host and a bounded stressor selection. Read the project warnings: privileged or excessive stress can destabilize the host. Capture the targeted resource and recovery evidence; stop every stressor and remove designated temporary artifacts. |
| [sysbench](https://github.com/akopytov/sysbench) | Compare system and database benchmarking workloads in a controllable test environment. | Intermediate; public project repository. Benchmarks can saturate resources or alter test data; isolate targets. | Requires sysbench and a disposable system or database target. Inspect the selected script and prepare/run/cleanup stages; retain workload and result evidence, then remove created test tables or files. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. | Requires two authorized endpoints, an iperf3 client/server, and permitted connectivity. Record direction, duration, throughput, retransmissions where reported, and host limits; stop the server and remove temporary network rules. |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. | Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Foundation to intermediate; driver and operating-system prerequisites vary. | Use the start guide’s cluster lifecycle instructions. Review driver-managed machines, volumes, and any external resources before declaring cleanup complete. |
| [Install Chaos Mesh using Helm](https://chaos-mesh.org/docs/production-installation-using-helm/) | Install the experiment controllers in a Kubernetes environment and verify the deployment before selecting a fault experiment. | Intermediate; public installation guide. Requires a cluster and Helm; use a disposable practice cluster before considering production targets. | Requires Helm and a disposable Kubernetes cluster with a supported runtime. Use the installation verification and Uninstall Chaos Mesh sections; inspect remaining experiment resources, namespaces, permissions, and persistent storage after removal. |

## Monitoring and recovery demonstrations

Use isolated data and provider boundaries. Inspect persistent storage and external dependencies during teardown.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [kube-prometheus](https://github.com/prometheus-operator/kube-prometheus) | Study manifests and dashboards for a Kubernetes monitoring stack. | Advanced; public implementation repository. Match supported Kubernetes versions and review resource use; remove the stack's resources when a practice cluster is retired. | Use the repository’s setup and teardown documentation for the selected release. Review persistent telemetry storage and cluster resources before retiring the environment. |
| [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/) | Practice basic metrics collection and querying. | Foundation to intermediate; a starter setup does not establish monitoring availability or retention design. | Stop the local practice server when finished and remove unneeded test configuration and data after reviewing any evidence you intend to keep. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. | Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. | This is a restore command reference, not a complete prebuilt lab. Requires a valid backup repository, matching database tools, permissions, and a separate restore target. Verify recovered data and recovery-point evidence; retire only test targets and never delete the source backup as routine cleanup. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Intermediate; use a sandbox account and review resource creation and removal per lab. | Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. | Read the workshop’s cleanup guidance and inspect cluster-related storage, networking, IAM, and managed services rather than removing only workloads. |

## Use the linked practice material

Choose the upstream exercise or example that matches your question and version. Before starting, identify the test environment, permissions, target scope, expected observation, stop condition, and resources it can create. Keep enough configuration and result evidence to explain what happened; do not keep credentials or sensitive production data in a public project.

If the expected result does not appear, use the source's diagnostic guidance to check prerequisites, versions, permissions, target selection, connectivity, and observation points. Cleanup is a separate verification: confirm fault removal and resource retirement, including retained storage and resources created outside the local environment. These links were reviewed as resources; the exercises were not executed for this directory.

[Browse the other collections](README.md#resource-collections)

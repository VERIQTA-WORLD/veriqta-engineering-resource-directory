# DevOps infrastructure engineer: labs, examples, and projects

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

[Role overview](README.md) · [DevOps delivery careers](../README.md) · [All careers](../../README.md)

## Machine and configuration experiments

Use throwaway machines or instances. Inspect privileged initialization, target inventory, and destruction instructions before practicing repeated runs or failures.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Vagrant getting-started tutorials](https://developer.hashicorp.com/vagrant/tutorials/getting-started) | Practice a local machine lifecycle, provisioning, and destruction using the provider's tutorials. | Foundation; public tutorials. Downloaded boxes and provisioners need review; destroy machines and clean retained artifacts as appropriate. Practice and cleanup: Follow the machine lifecycle and destruction tutorial in this collection. Review retained boxes, host files, and downloaded artifacts separately. |
| [cloud-init YAML examples](https://cloudinit.readthedocs.io/en/latest/reference/examples.html) | Inspect initialization examples before writing machine bootstrap configuration. | Intermediate; public examples. User data can run privileged commands; test on disposable instances and remove the instances afterward. Practice and cleanup: These are privileged initialization examples, not standalone safe labs. Use disposable instances; remove the instances and retained disks or images through the provider. |
| [Ansible example playbooks](https://github.com/ansible/ansible-examples) | Inspect project-maintained examples of application configuration and orchestration. | Intermediate; public example repository. Check age, target assumptions, and credentials; adapt in disposable systems rather than treating examples as production defaults. Practice and cleanup: Review the selected playbook and target inventory first. Configuration changes do not automatically undo themselves; use disposable targets and retire them afterward. |
| [Ansible Molecule](https://docs.ansible.com/projects/molecule/) | Evaluate scenarios for developing and testing Ansible collections, playbooks, and roles. | Intermediate; public documentation. Scenario drivers and targets determine infrastructure, privileges, and cleanup requirements. Practice and cleanup: Review the scenario create, converge, verify, and destroy playbooks. Confirm destruction of its actual target resources and any external dependencies. |
| [Packer tutorials](https://developer.hashicorp.com/packer/tutorials) | Find image-building walkthroughs and provider-specific examples. | Intermediate; public tutorial collection. Image builds require supported builders, credentials, compute, and removal of retained images. Practice and cleanup: Select a builder-specific tutorial before execution. Retire temporary build machines, retained images, snapshots, and storage according to that tutorial and provider. |

## Infrastructure testing and drift

Practice reviewing actual ownership, change previews, test assertions, and retained resources. Protect state and use a dedicated account or project boundary.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Terraform testing tutorial](https://developer.hashicorp.com/terraform/tutorials/configuration-language/test) | Practice assertions and test setup for infrastructure configuration. | Intermediate; public tutorial. Tests may provision infrastructure; inspect run modes, permissions, and teardown before execution. Practice and cleanup: Inspect the test run mode and generated resources. The tutorial explains ephemeral test infrastructure; investigate resources retained after interrupted or failed tests. |
| [Terraform refresh-only planning tutorial](https://developer.hashicorp.com/terraform/tutorials/state/refresh) | Practice examining infrastructure drift through the provider's state-refresh tutorial. | Intermediate; public tutorial. Example provisioning needs cloud credentials and can incur charges; follow the tutorial's destruction instructions. Practice and cleanup: Use the tutorial’s Clean up resources section; verify infrastructure removal before discarding its state and local workspace. |
| [Pulumi testing guide](https://www.pulumi.com/docs/iac/guides/testing/) | Compare unit, property, and integration approaches for infrastructure expressed as code. | Intermediate; public guide. Provider integration tests can create billable resources and require cleanup. Practice and cleanup: The guide distinguishes mocked unit tests from deployed integration tests. Verify ephemeral-resource destruction and inspect failed-test leftovers. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Public reference. Intermediate; use a sandbox account and review resource creation and removal per lab. Practice and cleanup: Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |

## Provider foundation implementations

These are infrastructure-heavy samples. Review identities, dependencies, resource costs, deletion behavior, and provider-specific cleanup before applying them.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Public reference. Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. Practice and cleanup: Read the workshop’s cleanup guidance and inspect cluster-related storage, networking, IAM, and managed services rather than removing only workloads. |
| [AKS baseline implementation](https://github.com/mspnp/aks-baseline) | Inspect the infrastructure sample accompanying the AKS baseline architecture. | Public reference. Advanced; review the repository's current instructions and required Azure resources before deploying. Practice and cleanup: Use the sample repository’s documented deployment and resource-removal guidance. Review Azure resources, retained data, identities, and shared dependencies before deletion. |
| [Google Cloud example foundation](https://github.com/terraform-google-modules/terraform-example-foundation) | Inspect infrastructure code for enterprise foundation patterns. | Public reference. Advanced; substantial organization, permission, and billing prerequisites. Treat as a reference implementation, not a starter lab. Practice and cleanup: This is an organization-level reference implementation. Review the repository’s destruction caveats and shared dependencies; agree what must remain before removing infrastructure. |
| [AWS Workshops](https://workshops.aws/) | Find workshops for architecture, security, networking, operations, and delivery topics. | Public reference. Intermediate; prerequisites, regional support, and AWS charges vary by workshop. Follow its cleanup instructions. Practice and cleanup: Choose a specific workshop and read its cleanup section before starting. Inspect compute, networking, storage, identities, and managed services left in the account. |

## Local cluster and infrastructure telemetry

Keep practice clusters separate from shared services. Review storage and external resource ownership so removing the cluster does not leave resources or lose needed data.

| Resource | What it helps you do | Level, access, and selection notes |
| --- | --- | --- |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Public reference. Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. Practice and cleanup: Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Public reference. Foundation to intermediate; driver and operating-system prerequisites vary. Practice and cleanup: Use the start guide’s cluster lifecycle instructions. Review driver-managed machines, volumes, and any external resources before declaring cleanup complete. |
| [kube-prometheus](https://github.com/prometheus-operator/kube-prometheus) | Study manifests and dashboards for a Kubernetes monitoring stack. | Advanced; public implementation repository. Match supported Kubernetes versions and review resource use; remove the stack's resources when a practice cluster is retired. Practice and cleanup: Use the repository’s setup and teardown documentation for the selected release. Review persistent telemetry storage and cluster resources before retiring the environment. |
| [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/) | Practice basic metrics collection and querying. | Public reference. Foundation to intermediate; a starter setup does not establish monitoring availability or retention design. Practice and cleanup: Stop the local practice server when finished and remove unneeded test configuration and data after reviewing any evidence you intend to keep. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Public reference. Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. Practice and cleanup: Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |

## Continue browsing

[Tool directory](toolkit.md) · [Official documentation](official-documentation.md) · [Reference architectures and design guidance](reference-architectures.md) · [Learning resources](learning-resources.md) · [Production responsibilities and operational resources](production-responsibilities.md) · [Standards and frameworks](standards-and-frameworks.md)

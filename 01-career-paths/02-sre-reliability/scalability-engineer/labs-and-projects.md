# Scalability engineer: labs, examples, and projects

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

## Browse this page

- [Workload and data-path experiments](#workload-and-data-path-experiments)
- [Cluster and observability environments](#cluster-and-observability-environments)
- [Provider and infrastructure practice](#provider-and-infrastructure-practice)

## Workload and data-path experiments

Use disposable targets with controlled data and explicit thresholds. Record generator utilization and the offered versus completed workload; remove generated data afterward.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [Running k6](https://grafana.com/docs/k6/latest/get-started/running-k6/) | Learn how to create and interpret initial load tests. | Intermediate; test only systems you own or are authorized to test. Start with controlled targets. | Run only against authorized targets. Stop the test, remove disposable targets, and review retained result files and any hosted-test usage separately. |
| [k6 arrival-rate executors](https://grafana.com/docs/k6/latest/using-k6/scenarios/concepts/arrival-rate-vu-allocation/) | Understand workload generation and virtual-user allocation for arrival-rate tests. | Intermediate; public reference. Generator capacity and dropped iterations can distort the apparent system limit. | Requires an installed k6 client, target, and enough generator capacity. Compare intended arrival rate with delivered work and dropped iterations; stop the test and retire its targets. |
| [k6 thresholds](https://grafana.com/docs/k6/latest/using-k6/thresholds/) | Define explicit load-test acceptance conditions rather than relying on a completed run. | Intermediate; public reference. Thresholds need a justified target, representative workload, and sufficient observations. | Requires an installed k6 client and an authorized disposable target. Keep the threshold definitions, workload, and exit/result evidence; stop the generator and remove disposable targets. |
| [Locust quick start](https://docs.locust.io/en/stable/quickstart.html) | Practice a Python-defined load test using project-maintained setup instructions. | Intermediate; public quick-start guide. The stable URL currently serves a development build; select documentation matching the installed Locust version and use authorized targets. | Requires Python, Locust, and an authorized target. Keep task definitions, observed request rate, errors, and generator limits; stop workers and remove the disposable target and data. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. | Requires PostgreSQL client tools and a disposable test database. Initialization changes database contents; compare transaction results, errors, and latency, then remove the test database deliberately. |
| [sysbench](https://github.com/akopytov/sysbench) | Compare system and database benchmarking workloads in a controllable test environment. | Intermediate; public project repository. Benchmarks can saturate resources or alter test data; isolate targets. | Requires sysbench and a disposable system or database target. Inspect the selected script and prepare/run/cleanup stages; retain workload and result evidence, then remove created test tables or files. |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. | Requires fio and carefully isolated test files or devices. Record the job definition, target, latency, throughput, and errors. Raw-device jobs can destroy data; stop jobs and remove only the designated test files. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. | Requires two authorized endpoints, an iperf3 client/server, and permitted connectivity. Record direction, duration, throughput, retransmissions where reported, and host limits; stop the server and remove temporary network rules. |
| [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) | Practice SQL and database concepts with the project's introductory material. | Foundation; public tutorial. Work in a disposable database, inspect statement effects, and remove practice data afterward. | Requires an installed or sandbox PostgreSQL instance and a disposable database. Keep SQL and expected query-result evidence; inspect every statement, then remove the practice database and local test data deliberately. |

## Cluster and observability environments

Observe scheduling, resource pressure, signal volume, and service behavior while changing demand. Remove test deployments and inspect retained storage.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. | Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Foundation to intermediate; driver and operating-system prerequisites vary. | Use the start guide’s cluster lifecycle instructions. Review driver-managed machines, volumes, and any external resources before declaring cleanup complete. |
| [kube-prometheus](https://github.com/prometheus-operator/kube-prometheus) | Study manifests and dashboards for a Kubernetes monitoring stack. | Advanced; public implementation repository. Match supported Kubernetes versions and review resource use; remove the stack's resources when a practice cluster is retired. | Use the repository’s setup and teardown documentation for the selected release. Review persistent telemetry storage and cluster resources before retiring the environment. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. | Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |
| [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/) | Practice basic metrics collection and querying. | Foundation to intermediate; a starter setup does not establish monitoring availability or retention design. | Stop the local practice server when finished and remove unneeded test configuration and data after reviewing any evidence you intend to keep. |

## Provider and infrastructure practice

Choose one workshop with a stated scope. Validate quotas, infrastructure behavior, and account cleanup rather than assuming the example covers every scaling limit.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. | Read the workshop’s cleanup guidance and inspect cluster-related storage, networking, IAM, and managed services rather than removing only workloads. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Intermediate; use a sandbox account and review resource creation and removal per lab. | Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |
| [AWS Workshops](https://workshops.aws/) | Find workshops for architecture, security, networking, operations, and delivery topics. | Intermediate; prerequisites, regional support, and AWS charges vary by workshop. Follow its cleanup instructions. | Choose a specific workshop and read its cleanup section before starting. Inspect compute, networking, storage, identities, and managed services left in the account. |
| [Terraform testing tutorial](https://developer.hashicorp.com/terraform/tutorials/configuration-language/test) | Practice assertions and test setup for infrastructure configuration. | Intermediate; public tutorial. Tests may provision infrastructure; inspect run modes, permissions, and teardown before execution. | Inspect the test run mode and generated resources. The tutorial explains ephemeral test infrastructure; investigate resources retained after interrupted or failed tests. |
| [Pulumi testing guide](https://www.pulumi.com/docs/iac/guides/testing/) | Compare unit, property, and integration approaches for infrastructure expressed as code. | Intermediate; public guide. Provider integration tests can create billable resources and require cleanup. | The guide distinguishes mocked unit tests from deployed integration tests. Verify ephemeral-resource destruction and inspect failed-test leftovers. |

## Use the linked practice material

Choose the upstream exercise or example that matches your question and version. Before starting, identify the test environment, permissions, target scope, expected observation, stop condition, and resources it can create. Keep enough configuration and result evidence to explain what happened; do not keep credentials or sensitive production data in a public project.

If the expected result does not appear, use the source's diagnostic guidance to check prerequisites, versions, permissions, target selection, connectivity, and observation points. Cleanup is a separate verification: confirm fault removal and resource retirement, including retained storage and resources created outside the local environment. These links were reviewed as resources; the exercises were not executed for this directory.

[Browse the other collections](README.md#resource-collections)

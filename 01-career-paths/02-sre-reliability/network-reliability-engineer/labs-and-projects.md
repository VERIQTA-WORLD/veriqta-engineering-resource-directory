# Network reliability engineer: labs, examples, and projects

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

## Browse this page

- [Isolated routing and connectivity practice](#isolated-routing-and-connectivity-practice)
- [Cluster DNS and workload traffic practice](#cluster-dns-and-workload-traffic-practice)
- [Provider connectivity and telemetry exercises](#provider-connectivity-and-telemetry-exercises)

## Isolated routing and connectivity practice

Use lab-only interfaces, routes, and addresses. OS images can have separate licensing or access requirements; remove topologies and stop all test endpoints afterward.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [containerlab quick start](https://containerlab.dev/quickstart/) | Practice a documented local topology deployment and inspection workflow. | Intermediate; public local topology lab. Requires a supported Linux environment and container runtime; the Arista cEOS example image requires a vendor account and separate download. | Requires a supported Linux environment, container runtime, and the selected images; the cEOS example needs a vendor account. Record deployed topology and reachability evidence; follow Destroying a lab, then inspect retained files, images, and temporary host networking. |
| [iperf3 documentation](https://software.es.net/iperf/) | Generate controlled throughput measurements between authorized network endpoints. | Intermediate; public project documentation. Traffic can saturate a path; coordinate endpoints and stop servers and tests afterward. | Requires two authorized endpoints, an iperf3 client/server, and permitted connectivity. Record direction, duration, throughput, retransmissions where reported, and host limits; stop the server and remove temporary network rules. |
| [Toxiproxy usage and API examples](https://github.com/Shopify/toxiproxy/blob/main/README.md) | Inspect proxy configuration and fault-control examples before writing a dependency-failure test. | Intermediate; public project examples. Reset faults and remove the disposable proxy; never intercept unrelated traffic. | Requires a Toxiproxy server, a client, and a disposable application dependency. Use the README API and toxic examples; retain the baseline, fault, and recovery results, then remove toxics/proxies and stop the server. |
| [Wireshark user guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Review capture setup, protocol analysis, display filtering, and packet inspection workflows. | Foundation to advanced; public manual currently displaying development version 4.7.4. Match the installed release; packet capture requires permission and careful handling of sensitive data. | Requires an authorized interface or approved test capture. Follow Capturing Live Network Data and Stopping a Capture; save only permitted evidence, stop capture processes, and handle or remove sensitive capture files under the agreed retention policy. |
| [tcpdump manual](https://www.tcpdump.org/manpages/tcpdump.1.html) | Check capture expressions, interface selection, output, and diagnostic options. | Intermediate; public CLI reference. Restrict collection to authorized traffic and define secure capture-file retention. | Requires tcpdump, appropriate capture privileges, and a permitted interface or capture file. Inspect filter and output options; stop the capture process and secure or remove test packet files after preserving approved evidence. |

## Cluster DNS and workload traffic practice

Use a dedicated cluster and diagnostic workloads. Review created pods, services, policy, and retained data during teardown.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. | Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Foundation to intermediate; driver and operating-system prerequisites vary. | Use the start guide’s cluster lifecycle instructions. Review driver-managed machines, volumes, and any external resources before declaring cleanup complete. |
| [Kubernetes DNS troubleshooting](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/) | Investigate workload DNS resolution through documented cluster diagnostic steps. | Intermediate; public task guide. Distinguish pod, service, resolver, and upstream failures; some steps create diagnostic workloads. | Requires kubectl access to a disposable cluster and permission for the documented test pod. Record pod DNS configuration and lookup results; remove the test pod and any temporary diagnostic resources after the investigation. |
| [Install Chaos Mesh using Helm](https://chaos-mesh.org/docs/production-installation-using-helm/) | Install the experiment controllers in a Kubernetes environment and verify the deployment before selecting a fault experiment. | Intermediate; public installation guide. Requires a cluster and Helm; use a disposable practice cluster before considering production targets. | Requires Helm and a disposable Kubernetes cluster with a supported runtime. Use the installation verification and Uninstall Chaos Mesh sections; inspect remaining experiment resources, namespaces, permissions, and persistent storage after removal. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. | Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |
| [Running k6](https://grafana.com/docs/k6/latest/get-started/running-k6/) | Learn how to create and interpret initial load tests. | Intermediate; test only systems you own or are authorized to test. Start with controlled targets. | Run only against authorized targets. Stop the test, remove disposable targets, and review retained result files and any hosted-test usage separately. |

## Provider connectivity and telemetry exercises

Select the networking exercise inside the provider collection. Read region, permissions, traffic charges, shared dependencies, and cleanup first.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [AWS Workshops](https://workshops.aws/) | Find workshops for architecture, security, networking, operations, and delivery topics. | Intermediate; prerequisites, regional support, and AWS charges vary by workshop. Follow its cleanup instructions. | Choose a specific workshop and read its cleanup section before starting. Inspect compute, networking, storage, identities, and managed services left in the account. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Intermediate; use a sandbox account and review resource creation and removal per lab. | Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |
| [Amazon EKS Workshop](https://www.eksworkshop.com/) | Explore EKS infrastructure and workload exercises. | Intermediate to advanced; requires Kubernetes and AWS knowledge. Review cluster and supporting-service costs. | Read the workshop’s cleanup guidance and inspect cluster-related storage, networking, IAM, and managed services rather than removing only workloads. |
| [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/) | Practice basic metrics collection and querying. | Foundation to intermediate; a starter setup does not establish monitoring availability or retention design. | Stop the local practice server when finished and remove unneeded test configuration and data after reviewing any evidence you intend to keep. |

## Use the linked practice material

Choose the upstream exercise or example that matches your question and version. Before starting, identify the test environment, permissions, target scope, expected observation, stop condition, and resources it can create. Keep enough configuration and result evidence to explain what happened; do not keep credentials or sensitive production data in a public project.

If the expected result does not appear, use the source's diagnostic guidance to check prerequisites, versions, permissions, target selection, connectivity, and observation points. Cleanup is a separate verification: confirm fault removal and resource retirement, including retained storage and resources created outside the local environment. These links were reviewed as resources; the exercises were not executed for this directory.

[Browse the other collections](README.md#resource-collections)

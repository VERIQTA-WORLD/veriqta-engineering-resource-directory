# Database reliability engineer: labs, examples, and projects

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Find practical environments, examples, workshops, and reference implementations. They have been reviewed as linked resources, not executed as part of this directory. Read the upstream prerequisites, permissions, effects, cost conditions, and teardown instructions before running them.

## Browse this page

- [Query, connection, and workload practice](#query-connection-and-workload-practice)
- [Failover and restore practice](#failover-and-restore-practice)
- [Telemetry and provider practice](#telemetry-and-provider-practice)

## Query, connection, and workload practice

Use a disposable database and representative test data. Initialization, query analysis, benchmarks, and connection faults can change data or consume substantial resources.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) | Practice SQL and database concepts with the project's introductory material. | Foundation; public tutorial. Work in a disposable database, inspect statement effects, and remove practice data afterward. | Requires an installed or sandbox PostgreSQL instance and a disposable database. Keep SQL and expected query-result evidence; inspect every statement, then remove the practice database and local test data deliberately. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. | Requires PostgreSQL client tools and a disposable test database. Initialization changes database contents; compare transaction results, errors, and latency, then remove the test database deliberately. |
| [sysbench](https://github.com/akopytov/sysbench) | Compare system and database benchmarking workloads in a controllable test environment. | Intermediate; public project repository. Benchmarks can saturate resources or alter test data; isolate targets. | Requires sysbench and a disposable system or database target. Inspect the selected script and prepare/run/cleanup stages; retain workload and result evidence, then remove created test tables or files. |
| [Toxiproxy usage and API examples](https://github.com/Shopify/toxiproxy/blob/main/README.md) | Inspect proxy configuration and fault-control examples before writing a dependency-failure test. | Intermediate; public project examples. Reset faults and remove the disposable proxy; never intercept unrelated traffic. | Requires a Toxiproxy server, a client, and a disposable application dependency. Use the README API and toxic examples; retain the baseline, fault, and recovery results, then remove toxics/proxies and stop the server. |
| [Testcontainers](https://testcontainers.com/guides/) | Find guides for container-backed integration test dependencies. | Intermediate; runtime and language-library requirements vary. Tests still need meaningful assertions. | Requires a supported runtime and the chosen language integration. Use disposable fixtures; retain assertion results, check the integration's lifecycle cleanup, and inspect containers, volumes, networks, and any external resources afterward. |
| [Locust quick start](https://docs.locust.io/en/stable/quickstart.html) | Practice a Python-defined load test using project-maintained setup instructions. | Intermediate; public quick-start guide. The stable URL currently serves a development build; select documentation matching the installed Locust version and use authorized targets. | Requires Python, Locust, and an authorized target. Keep task definitions, observed request rate, errors, and generator limits; stop workers and remove the disposable target and data. |

## Failover and restore practice

Run these in isolated environments with copied or synthetic data. Verify data and application outcomes before accepting recovery, then remove test coordination and backup storage deliberately.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [Patroni quick start and examples](https://github.com/patroni/patroni) | Inspect project-maintained setup examples and high-availability component relationships. | Advanced; public source repository. Examples need disposable hosts or containers; remove test databases, coordination state, and retained volumes deliberately. | Requires PostgreSQL, Python dependencies, and a supported distributed configuration store. Review Running and Configuring and example YAML; verify leadership and application behavior, then stop all test members and remove designated coordination and database data. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. | This is a restore command reference, not a complete prebuilt lab. Requires a valid backup repository, matching database tools, permissions, and a separate restore target. Verify recovered data and recovery-point evidence; retire only test targets and never delete the source backup as routine cleanup. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. | This is an archiving and point-in-time recovery guide. Requires PostgreSQL, a valid base backup, and required archived WAL. Restore only to an isolated target; record the recovery point and data checks, then remove test data without deleting archives still needed for retention. |
| [Redis Sentinel](https://redis.io/docs/latest/operate/oss_and_stack/management/sentinel/) | Review Redis monitoring and failover coordination in the documented Sentinel model. | Advanced; public reference. Clients, quorum arrangements, and network partitions affect failover outcomes. | Requires isolated Redis and Sentinel processes and writable configurations. Use Sentinel quick start and deployment guidance; verify leadership and client behavior, then stop every test process and retire only the practice configuration and data. |

## Telemetry and provider practice

Choose database-related workshops and examples rather than deploy unrelated stacks. Review charges, data exposure, permissions, and teardown for the chosen environment.

| Resource | Practice focus | Level and access | Prerequisites, evidence, and cleanup pointers |
| --- | --- | --- | --- |
| [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/) | Practice basic metrics collection and querying. | Foundation to intermediate; a starter setup does not establish monitoring availability or retention design. | Stop the local practice server when finished and remove unneeded test configuration and data after reviewing any evidence you intend to keep. |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore instrumented services and telemetry flows in a demonstrator. | Intermediate; resource usage and deployment prerequisites vary. Demo defaults are not production settings. | Check the selected Docker or Kubernetes deployment instructions. Stop and remove the demo deployment, then review retained storage and exported telemetry. |
| [AWS Workshops](https://workshops.aws/) | Find workshops for architecture, security, networking, operations, and delivery topics. | Intermediate; prerequisites, regional support, and AWS charges vary by workshop. Follow its cleanup instructions. | Choose a specific workshop and read its cleanup section before starting. Inspect compute, networking, storage, identities, and managed services left in the account. |
| [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/) | Practice workload review and improvements tied to architecture concerns. | Intermediate; use a sandbox account and review resource creation and removal per lab. | Follow the selected lab’s cleanup instructions and check the sandbox account for retained billable resources. |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. | Follow the quick-start cluster deletion instructions; inspect retained local images, volumes, and externally provisioned resources separately. |

## Use the linked practice material

Choose the upstream exercise or example that matches your question and version. Before starting, identify the test environment, permissions, target scope, expected observation, stop condition, and resources it can create. Keep enough configuration and result evidence to explain what happened; do not keep credentials or sensitive production data in a public project.

If the expected result does not appear, use the source's diagnostic guidance to check prerequisites, versions, permissions, target selection, connectivity, and observation points. Cleanup is a separate verification: confirm fault removal and resource retirement, including retained storage and resources created outside the local environment. These links were reviewed as resources; the exercises were not executed for this directory.

[Browse the other collections](README.md#resource-collections)

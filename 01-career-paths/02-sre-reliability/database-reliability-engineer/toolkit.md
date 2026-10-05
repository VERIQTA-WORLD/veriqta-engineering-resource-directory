# Database reliability engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Database and coordination systems](#database-and-coordination-systems)
- [PostgreSQL availability, pooling, and recovery](#postgresql-availability-pooling-and-recovery)
- [Database and application telemetry](#database-and-application-telemetry)
- [Fault tests and repeatable environments](#fault-tests-and-repeatable-environments)
- [Identity, credentials, and storage investigation](#identity-credentials-and-storage-investigation)

## Database and coordination systems

Choose sources matching the database actually operated. Relational databases, caches, messaging systems, and coordination stores offer different data and failure guarantees.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL documentation](https://www.postgresql.org/docs/current/) | Locate administration, SQL, replication, security, and operating references for PostgreSQL. | Foundation onward; public documentation. The current alias tracks a changing major version; use the manual for the installed server. |
| [MySQL reference manual](https://dev.mysql.com/doc/refman/8.4/en/) | Find database administration, InnoDB, replication, security, and recovery references. | Intermediate; public version-specific manual for MySQL 8.4. Use the manual matching the deployed release. |
| [Redis documentation](https://redis.io/docs/latest/) | Find command, deployment, persistence, replication, and operating references for Redis products. | Foundation onward; public documentation. Distinguish product editions and deployment models; review applicable terms separately. |
| [MongoDB self-managed operations checklist](https://www.mongodb.com/docs/manual/administration/production-checklist-operations/) | Review operational considerations for a MongoDB deployment. | Intermediate to advanced; public checklist for self-managed deployments. Managed-service responsibilities and deployment-specific limits differ. |
| [Apache Cassandra documentation](https://cassandra.apache.org/doc/latest/) | Explore distributed database architecture, repair, consistency, and operations. | Advanced; public project documentation. Use the deployed release; replica health and consistency choices affect reads, writes, and repair. |
| [Apache Kafka operations documentation](https://kafka.apache.org/43/operations/) | Review messaging durability, replication, configuration, and operating interfaces. | Advanced; public Apache project documentation for Kafka 4.3. Select the deployed version; broker, client, storage, and coordination changes require separate review. |
| [etcd documentation](https://etcd.io/docs/) | Review distributed coordination, maintenance, recovery, and failure behavior. | Advanced; public versioned reference collection. Quorum, disk latency, and recovery state need explicit operating plans. |

## PostgreSQL availability, pooling, and recovery

Compare failover orchestration, connection mediation, backups, and archiving as distinct responsibilities. None replaces validation of the recovered data.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Patroni documentation](https://patroni.readthedocs.io/en/latest/) | Compare PostgreSQL high-availability orchestration and its distributed coordination dependencies. | Advanced; public project reference. Review fencing, datastore behavior, failover policy, and recovery; an orchestrator is not a backup. |
| [PgBouncer documentation](https://www.pgbouncer.org/config.html) | Compare connection pooling behavior, resource settings, and application compatibility. | Intermediate; public configuration reference. Pooling mode and session-dependent application features affect correctness. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [PostgreSQL Exporter](https://github.com/prometheus-community/postgres_exporter) | Explore PostgreSQL metrics collection for a Prometheus-based operating stack. | Intermediate; public project repository. Review database privileges, supported queries, and collection overhead. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. |
| [sysbench](https://github.com/akopytov/sysbench) | Compare system and database benchmarking workloads in a controllable test environment. | Intermediate; public project repository. Benchmarks can saturate resources or alter test data; isolate targets. |

## Database and application telemetry

Correlate database activity with request and dependency behavior. Exporter health alone cannot establish database availability or correct transactions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Sloth](https://sloth.dev/) | Compare an SLO-to-Prometheus rule generator for service monitoring workflows. | Intermediate; public project documentation. Correct generated rules still require valid indicators and label boundaries. |
| [Pyrra](https://github.com/pyrra-dev/pyrra) | Evaluate SLO definition and visualization tooling around Prometheus-based measurements. | Intermediate; public project repository. Review deployment requirements and the service's actual measurement coverage. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |

## Fault tests and repeatable environments

Use isolated database and application environments for latency, connection, load, and recovery experiments. Inspect generated data and retained volumes.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |
| [Testcontainers](https://testcontainers.com/guides/) | Find guides for container-backed integration test dependencies. | Intermediate; runtime and language-library requirements vary. Tests still need meaningful assertions. |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |

## Identity, credentials, and storage investigation

Review database privileges and secret distribution separately from host or storage performance. A secret store does not configure database authorization.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [SOPS](https://github.com/getsops/sops) | Review encrypted configuration-file workflows with supported key services. | Intermediate; key distribution and access control remain your responsibility. Decrypted content can still leak. |
| [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/) | Review managed secret storage, access, rotation, and service integrations. | Intermediate; review IAM, rotation support, availability dependencies, and usage charges. |
| [Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/) | Review managed secrets, keys, certificates, and access guidance. | Intermediate; choose the relevant object and access model and plan recovery and billing. |
| [Google Cloud Secret Manager](https://cloud.google.com/secret-manager/docs) | Review managed secret versions, access, and application integration. | Intermediate; evaluate identity scope, version lifecycle, availability dependencies, and billing. |
| [fio documentation](https://fio.readthedocs.io/en/latest/) | Design controlled storage workload tests and interpret latency and throughput reports. | Advanced; public workload-generator manual currently built from a development revision. Use version-matched options and disposable test files; raw-device jobs can destroy data. |
| [Linux perf tutorial](https://perfwiki.github.io/main/tutorial/) | Explore counter collection, sampling, reports, and diagnostic checks using the perf project's tutorial. | Advanced; public project tutorial with historical example output. Match kernel and perf versions; permissions, hardware events, symbols, and sampling overhead affect results. |
| [BCC tools and examples](https://github.com/iovisor/bcc) | Explore eBPF-based tracing utilities for investigating operating-system behavior. | Advanced; public project repository. Tool support depends on kernel and build requirements; review privileges and collection overhead. |
| [jq manual](https://jqlang.org/manual/) | Inspect and transform JSON returned by command-line clients and infrastructure APIs. | Foundation onward; publicly readable manual. Validate missing fields rather than assuming one provider response shape. |

[Browse the other collections](README.md#resource-collections)

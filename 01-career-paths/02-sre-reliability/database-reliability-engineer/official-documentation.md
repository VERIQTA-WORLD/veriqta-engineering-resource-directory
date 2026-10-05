# Database reliability engineer: official documentation

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use these primary references to check implementation details and operating behavior. Select documentation matching your installed versions and provider; a latest-version URL can change over time.

## Browse this page

- [PostgreSQL diagnosis and maintenance](#postgresql-diagnosis-and-maintenance)
- [Replication, archives, and restores](#replication-archives-and-restores)
- [Other database and data-service references](#other-database-and-data-service-references)
- [Telemetry and access evidence](#telemetry-and-access-evidence)

## PostgreSQL diagnosis and maintenance

Investigate real activity, waits, execution plans, locks, and maintenance state before a disruptive corrective action. Use the installed version's manual.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [PostgreSQL explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html) | Understand lock conflicts and deadlock behavior before intervening in blocked database work. | Intermediate; public reference. Terminating a session can abort transactions and affect application behavior. |
| [PostgreSQL EXPLAIN guidance](https://www.postgresql.org/docs/current/using-explain.html) | Read execution plans and investigate query behavior with documented planner concepts. | Intermediate; public guide. EXPLAIN ANALYZE executes the query; use controlled targets for statements with side effects. |
| [PostgreSQL routine vacuuming](https://www.postgresql.org/docs/current/routine-vacuuming.html) | Investigate maintenance, dead tuples, statistics, and transaction-ID safety concerns. | Intermediate; public guide. Maintenance changes can affect I/O and locks; review the installed version's behavior. |
| [PgBouncer documentation](https://www.pgbouncer.org/config.html) | Compare connection pooling behavior, resource settings, and application compatibility. | Intermediate; public configuration reference. Pooling mode and session-dependent application features affect correctness. |
| [PostgreSQL Exporter](https://github.com/prometheus-community/postgres_exporter) | Explore PostgreSQL metrics collection for a Prometheus-based operating stack. | Intermediate; public project repository. Review database privileges, supported queries, and collection overhead. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. |

## Replication, archives, and restores

Read the full recovery and failover dependency chain. Define ownership of coordination, fencing, archive retention, and application reconnection.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Advanced; use documentation matching the deployed database version and test restored data. |
| [Patroni documentation](https://patroni.readthedocs.io/en/latest/) | Compare PostgreSQL high-availability orchestration and its distributed coordination dependencies. | Advanced; public project reference. Review fencing, datastore behavior, failover policy, and recovery; an orchestrator is not a backup. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. |
| [etcd documentation](https://etcd.io/docs/) | Review distributed coordination, maintenance, recovery, and failure behavior. | Advanced; public versioned reference collection. Quorum, disk latency, and recovery state need explicit operating plans. |

## Other database and data-service references

Use each system's own consistency, persistence, replication, and maintenance guidance. Do not transfer a PostgreSQL runbook to Redis or Cassandra.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [MySQL reference manual](https://dev.mysql.com/doc/refman/8.4/en/) | Find database administration, InnoDB, replication, security, and recovery references. | Intermediate; public version-specific manual for MySQL 8.4. Use the manual matching the deployed release. |
| [MySQL Performance Schema](https://dev.mysql.com/doc/refman/8.4/en/performance-schema.html) | Investigate instrumented database execution and resource use through the supported diagnostic system. | Advanced; public version-specific reference. Instrumentation, privileges, and overhead need review. |
| [MySQL replication reference](https://dev.mysql.com/doc/refman/8.4/en/replication.html) | Review replication arrangements and failure-sensitive operating behavior. | Advanced; public manual. Replication consistency and recovery depend on the chosen configuration and topology. |
| [Redis documentation](https://redis.io/docs/latest/) | Find command, deployment, persistence, replication, and operating references for Redis products. | Foundation onward; public documentation. Distinguish product editions and deployment models; review applicable terms separately. |
| [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/) | Compare persistence modes and their durability and restart implications. | Intermediate; public guide. Persisted data and replicas are not proof of tested recovery or acceptable data loss. |
| [Redis Sentinel](https://redis.io/docs/latest/operate/oss_and_stack/management/sentinel/) | Review Redis monitoring and failover coordination in the documented Sentinel model. | Advanced; public reference. Clients, quorum arrangements, and network partitions affect failover outcomes. |
| [MongoDB self-managed operations checklist](https://www.mongodb.com/docs/manual/administration/production-checklist-operations/) | Review operational considerations for a MongoDB deployment. | Intermediate to advanced; public checklist for self-managed deployments. Managed-service responsibilities and deployment-specific limits differ. |
| [Apache Cassandra documentation](https://cassandra.apache.org/doc/latest/) | Explore distributed database architecture, repair, consistency, and operations. | Advanced; public project documentation. Use the deployed release; replica health and consistency choices affect reads, writes, and repair. |
| [Apache Kafka operations documentation](https://kafka.apache.org/43/operations/) | Review messaging durability, replication, configuration, and operating interfaces. | Advanced; public Apache project documentation for Kafka 4.3. Select the deployed version; broker, client, storage, and coordination changes require separate review. |

## Telemetry and access evidence

Interpret queries and exported observations with permissions, timing, and sensitive data in mind.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [Prometheus instrumentation practices](https://prometheus.io/docs/practices/instrumentation/) | Select metrics and labels that answer operating questions without uncontrolled cardinality. | Intermediate; public guide. Instrumentation overhead and confidential label values need review. |
| [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) | Review telemetry reception, processing, export, and deployment concerns. | Intermediate; size for throughput and failure conditions and evaluate sensitive-data handling. |
| [AWS IAM security best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) | Review identity, permissions, credentials, and access-management guidance. | Intermediate; combine with service-specific permissions and organization policies. |
| [Microsoft identity platform documentation](https://learn.microsoft.com/en-us/entra/identity-platform/) | Review application identity, authentication, and integration concepts. | Intermediate to advanced; application identity and infrastructure authorization are separate concerns. |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Review Google Cloud access-control concepts and resource relationships. | Intermediate; validate actual permissions at the required resource scope. |

[Browse the other collections](README.md#resource-collections)

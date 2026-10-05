# Database reliability engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Diagnose queries, contention, and connection pressure](#diagnose-queries-contention-and-connection-pressure)
- [Operate replication and failover safely](#operate-replication-and-failover-safely)
- [Prove restore capability and integrity](#prove-restore-capability-and-integrity)
- [Control risk, objectives, and incident learning](#control-risk-objectives-and-incident-learning)

## Diagnose queries, contention, and connection pressure

Gather waits, plans, sessions, pooling state, and recent changes. Identify the affected transactions before terminating sessions or changing global settings.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |
| [PostgreSQL explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html) | Understand lock conflicts and deadlock behavior before intervening in blocked database work. | Intermediate; public reference. Terminating a session can abort transactions and affect application behavior. |
| [PostgreSQL EXPLAIN guidance](https://www.postgresql.org/docs/current/using-explain.html) | Read execution plans and investigate query behavior with documented planner concepts. | Intermediate; public guide. EXPLAIN ANALYZE executes the query; use controlled targets for statements with side effects. |
| [PgBouncer documentation](https://www.pgbouncer.org/config.html) | Compare connection pooling behavior, resource settings, and application compatibility. | Intermediate; public configuration reference. Pooling mode and session-dependent application features affect correctness. |
| [MySQL Performance Schema](https://dev.mysql.com/doc/refman/8.4/en/performance-schema.html) | Investigate instrumented database execution and resource use through the supported diagnostic system. | Advanced; public version-specific reference. Instrumentation, privileges, and overhead need review. |
| [PostgreSQL routine vacuuming](https://www.postgresql.org/docs/current/routine-vacuuming.html) | Investigate maintenance, dead tuples, statistics, and transaction-ID safety concerns. | Intermediate; public guide. Maintenance changes can affect I/O and locks; review the installed version's behavior. |

## Operate replication and failover safely

Track replication and archive health, coordination, fencing, and client reconnection. Test split or partition behavior using the chosen database's operating model.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [Patroni documentation](https://patroni.readthedocs.io/en/latest/) | Compare PostgreSQL high-availability orchestration and its distributed coordination dependencies. | Advanced; public project reference. Review fencing, datastore behavior, failover policy, and recovery; an orchestrator is not a backup. |
| [MySQL replication reference](https://dev.mysql.com/doc/refman/8.4/en/replication.html) | Review replication arrangements and failure-sensitive operating behavior. | Advanced; public manual. Replication consistency and recovery depend on the chosen configuration and topology. |
| [Redis Sentinel](https://redis.io/docs/latest/operate/oss_and_stack/management/sentinel/) | Review Redis monitoring and failover coordination in the documented Sentinel model. | Advanced; public reference. Clients, quorum arrangements, and network partitions affect failover outcomes. |
| [etcd documentation](https://etcd.io/docs/) | Review distributed coordination, maintenance, recovery, and failure behavior. | Advanced; public versioned reference collection. Quorum, disk latency, and recovery state need explicit operating plans. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |

## Prove restore capability and integrity

Maintain restore evidence for the required recovery point and verify data correctness and application behavior. A successful backup job is only one part of that evidence.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL continuous archiving and recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) | Review write-ahead log archiving, recovery configuration, and recovery dependencies. | Advanced; public reference. Restore correctness requires the needed base backup and complete relevant archive history. |
| [PostgreSQL backup and restore](https://www.postgresql.org/docs/current/backup.html) | Review database backup approaches and their operational implications. | Advanced; use documentation matching the deployed database version and test restored data. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [pgBackRest command reference](https://pgbackrest.org/command.html) | Check command options for controlled backup and restore experiments. | Advanced; public CLI reference. Restore operations can replace database files; use an isolated target and retire only designated test storage, preserving required source backups. |
| [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/) | Compare persistence modes and their durability and restart implications. | Intermediate; public guide. Persisted data and replicas are not proof of tested recovery or acceptable data loss. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [GitLab database incident postmortem](https://about.gitlab.com/blog/gitlab-dot-com-database-incident/) | Study operational mistakes, recovery dependencies, and backup-validation lessons in an original report. | Intermediate; public historical incident account. Do not confuse configured backup procedures with demonstrated restore capability. |

## Control risk, objectives, and incident learning

Review maintenance, credentials, change approval, and the customer impact of latency, failed transactions, or stale results. Preserve evidence and use historical incidents accurately.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [SLO engineering case studies](https://sre.google/workbook/slo-engineering-case-studies/) | Compare service-objective decisions and measurement approaches in concrete cases. | Intermediate; public chapter. Keep the service boundary and user expectations explicit. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |
| [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/) | Study duplicate-request handling and API design trade-offs. | Advanced; operation semantics determine which retry behavior is safe. |
| [GitHub October 2018 incident analysis](https://github.blog/news-insights/company-news/oct21-post-incident-analysis/) | Read the original incident analysis of database topology and recovery decisions. | Advanced; public historical report. Findings describe that incident and architecture, not a current service guarantee. |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Intermediate; cost work requires billing and usage data, not estimates alone. |

[Browse the other collections](README.md#resource-collections)

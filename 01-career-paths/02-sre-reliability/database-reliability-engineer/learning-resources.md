# Database reliability engineer: learning resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Browse by the problem or topic you need to understand. These are topic collections, not a compulsory learning sequence. Provider descriptions and publicly available chapters were reviewed; paid books and entire courses were not evaluated in full.

## Browse this page

- [Database foundations and deeper design](#database-foundations-and-deeper-design)
- [Query and operations learning](#query-and-operations-learning)
- [Reliability, consistency, and original incidents](#reliability-consistency-and-original-incidents)

## Database foundations and deeper design

Browse SQL fundamentals, database-system courses, and data-design references according to current knowledge. University projects can require substantial programming work.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html) | Practice SQL and database concepts with the project's introductory material. | Foundation; public tutorial. Work in a disposable database, inspect statement effects, and remove practice data afterward. |
| [PostgreSQL documentation](https://www.postgresql.org/docs/current/) | Locate administration, SQL, replication, security, and operating references for PostgreSQL. | Foundation onward; public documentation. The current alias tracks a changing major version; use the manual for the installed server. |
| [MySQL reference manual](https://dev.mysql.com/doc/refman/8.4/en/) | Find database administration, InnoDB, replication, security, and recovery references. | Intermediate; public version-specific manual for MySQL 8.4. Use the manual matching the deployed release. |
| [Designing Data-Intensive Applications](https://dataintensive.net/) | Find the author's book information and supporting resources for data-system design. | Intermediate to advanced; public book website. Full books are separate purchases; choose an edition and check publication details. |
| [CMU database systems course site](https://15445.courses.cs.cmu.edu/) | Find university database-system lectures, readings, and project guidance. | Advanced; public course discovery site. Semester content changes; programming and database foundations are prerequisites. |

## Query and operations learning

Use these to connect query behavior, locks, maintenance, and replication to service outcomes and diagnostic evidence.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PostgreSQL EXPLAIN guidance](https://www.postgresql.org/docs/current/using-explain.html) | Read execution plans and investigate query behavior with documented planner concepts. | Intermediate; public guide. EXPLAIN ANALYZE executes the query; use controlled targets for statements with side effects. |
| [PostgreSQL explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html) | Understand lock conflicts and deadlock behavior before intervening in blocked database work. | Intermediate; public reference. Terminating a session can abort transactions and affect application behavior. |
| [PostgreSQL routine vacuuming](https://www.postgresql.org/docs/current/routine-vacuuming.html) | Investigate maintenance, dead tuples, statistics, and transaction-ID safety concerns. | Intermediate; public guide. Maintenance changes can affect I/O and locks; review the installed version's behavior. |
| [PostgreSQL high availability and replication](https://www.postgresql.org/docs/current/high-availability.html) | Compare replication and standby arrangements, failure behavior, and responsibility boundaries. | Advanced; public reference. Replication lag, failover fencing, and application reconnection affect actual availability. |
| [MySQL Performance Schema](https://dev.mysql.com/doc/refman/8.4/en/performance-schema.html) | Investigate instrumented database execution and resource use through the supported diagnostic system. | Advanced; public version-specific reference. Instrumentation, privileges, and overhead need review. |
| [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/) | Compare persistence modes and their durability and restart implications. | Intermediate; public guide. Persisted data and replicas are not proof of tested recovery or acceptable data loss. |

## Reliability, consistency, and original incidents

Study service methods alongside data-specific cases. Keep historical findings tied to their tested versions and original incident scope.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Site Reliability Engineering](https://sre.google/sre-book/table-of-contents/) | Read original material on service objectives, risk, toil, monitoring, and operational engineering. | Intermediate; openly readable. Translate examples to your team size and system constraints. |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Study implementation-oriented reliability practices and case studies. | Intermediate to advanced; openly readable. Requires familiarity with service operation. |
| [Data integrity: what you read is what you wrote](https://sre.google/sre-book/data-integrity/) | Investigate durability, corruption detection, and integrity as distinct reliability concerns. | Advanced; public chapter. Replication and availability do not prove correct data or successful recovery. |
| [Distributed consensus for reliability](https://sre.google/sre-book/managing-critical-state/) | Study critical state, consensus, and the operational consequences of distributed coordination. | Advanced; public chapter. Quorum assumptions differ from ordinary replica-count assumptions. |
| [Jepsen analyses](https://jepsen.io/analyses) | Read independent system-consistency investigations and their tested assumptions. | Advanced; public research collection. Findings are tied to tested versions and scenarios; do not transfer a historical verdict to every later release. |
| [GitHub October 2018 incident analysis](https://github.blog/news-insights/company-news/oct21-post-incident-analysis/) | Read the original incident analysis of database topology and recovery decisions. | Advanced; public historical report. Findings describe that incident and architecture, not a current service guarantee. |
| [GitLab database incident postmortem](https://about.gitlab.com/blog/gitlab-dot-com-database-incident/) | Study operational mistakes, recovery dependencies, and backup-validation lessons in an original report. | Intermediate; public historical incident account. Do not confuse configured backup procedures with demonstrated restore capability. |

[Browse the other collections](README.md#resource-collections)

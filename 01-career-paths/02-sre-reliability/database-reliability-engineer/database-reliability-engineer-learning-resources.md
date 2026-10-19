# Database Reliability Engineer: Learning Resources

Study replication and transaction behavior before treating a standby as a recovery solution. Follow the statistics into an isolated restoration exercise, then connect client concurrency to database capacity.

## Understand replication trade-offs

Read [PostgreSQL: High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/high-availability.html), beginning with the comparison of approaches, then the applicable replication section.

Compare the selected replication approach with the freshness, durability, and writer-authority requirements.

## Read activity correctly

Read [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html), beginning with the relevant activity, replication, I/O, or database statistics views.

Identify the views and time context needed to distinguish connection pressure, waits, replication behavior, and useful work.

## Plan isolated restoration

Read [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html), beginning with base backup prerequisites, archiving, and recovery configuration.

Document base-backup requirements, WAL continuity, target configuration, and application validation.

## Connect clients to capacity

Read [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html), beginning with connection settings and their resource implications.

Explain the interaction among connection settings, application concurrency, memory, and observed throughput.

Choose a [project](database-reliability-engineer-labs-and-portfolio-projects.md) when you need execution evidence, or work through the [assessment scenarios](database-reliability-engineer-interview-and-assessment-resources.md) to apply the idea under changed conditions.

[Back to Database Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

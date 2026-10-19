# Database Reliability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for protecting database correctness, availability, performance, and recoverability as connected responsibilities. Match the installed version and actual configuration before interpreting an observation.

## What replication behavior applies?

Match the engine release, topology, configuration, and observed standby state.

Read [PostgreSQL: High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/high-availability.html), starting with the comparison of approaches, then the applicable replication section. Replication choices affect consistency and failure behavior; replication is not a substitute for backups.

## Can you recover to the selected point?

Check backup suitability, WAL continuity, credentials, target setup, and isolated validation.

Read [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html), starting with base backup prerequisites, archiving, and recovery configuration. Restore into a separate target; archived WAL availability and continuity affect recoverability.

## What does this activity observation mean?

Read the view semantics, visibility rules, reset context, and sampling interval.

Read [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html), starting with the relevant activity, replication, I/O, or database statistics views. Visibility depends on permissions and view semantics; counters and sampled observations need context.

[Back to Database Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

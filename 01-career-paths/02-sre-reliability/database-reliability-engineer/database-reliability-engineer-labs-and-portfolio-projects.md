# Database Reliability Engineer: Labs and Portfolio Projects

## Restore a PostgreSQL dataset to an isolated target

Use synthetic records to examine base-backup and archive prerequisites and validate usable restored data.

### Set up the exercise

Use dedicated PostgreSQL instances, a version-matched backup method, adequate storage, synthetic records, and explicit access to backup material.

### Investigate the behavior

Choose a recovery target in the lab. Verify archive coverage before attempting recovery; preserve the source backup and do not overwrite the only recovery material.

Keep backup and WAL identities, target configuration, timing, expected records, observed records, application checks, and remaining gaps.

### Finish and clean up

Stop and remove only the dedicated restored instance and exercise data. Remove disposable credentials and retain source material according to the lab plan.

### References for this project

- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) · [Prerequisites and limitations](../README.md#source-pg-pitr)
- [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html) · [Prerequisites and limitations](../README.md#source-pg-stats)
- [PostgreSQL: High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/high-availability.html) · [Prerequisites and limitations](../README.md#source-pg-ha)

## Investigate connection pressure

Observe useful database work while changing bounded client concurrency against synthetic transactions.

### Set up the exercise

Use a dedicated database, synthetic workload, activity-view access, resource telemetry, and strict load and duration limits.

### Investigate the behavior

Compare two concurrency levels and one controlled long-running operation. Do not infer improvement from connection count alone.

Record useful completions, errors, transaction timing, waits, connections, and resource observations. Explain the limiting mechanism and a proposed client or server change.

### Finish and clean up

Stop clients and restore changed configuration. Remove synthetic data and dedicated instances when finished.

### References for this project

- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html) · [Prerequisites and limitations](../README.md#source-pg-conn)
- [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html) · [Prerequisites and limitations](../README.md#source-pg-stats)
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/) · [Prerequisites and limitations](../README.md#source-overload)

[Back to Database Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

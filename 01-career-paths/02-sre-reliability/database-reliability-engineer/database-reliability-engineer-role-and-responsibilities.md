# Database Reliability Engineer: Role and Responsibility Resources

A database can accept connections and still fail the service through incorrect results, stale reads, blocked work, or unrecoverable data.

## Keep correctness in the availability discussion

Define which reads and writes must remain correct during replication, failover, and recovery. Compare durability and freshness requirements with application behavior. Fast recovery to an inconsistent state may fail the service objective even when the database accepts connections.

## Connect workload and resource behavior

Inspect queries, transactions, locks, connection activity, storage, and replication together. Application retries and connection growth can amplify pressure. Coordinate changes with application owners rather than treating server settings as the only available intervention.

## Own restore evidence

Define backup coverage, archive continuity, retention, restore targets, and validation. Keep recovery authority and key access available. Establish how you will verify expected data and application compatibility before restoring normal traffic.

## Resources behind these responsibilities

- [PostgreSQL: High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/high-availability.html): The comparison of approaches, then the applicable replication section. [Access and technical limits](../README.md#source-pg-ha).
- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html): Base backup prerequisites, archiving, and recovery configuration. [Access and technical limits](../README.md#source-pg-pitr).
- [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html): The relevant activity, replication, I/O, or database statistics views. [Access and technical limits](../README.md#source-pg-stats).
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html): Connection settings and their resource implications. [Access and technical limits](../README.md#source-pg-conn).
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/): Load shedding, request handling, and overload controls. [Access and technical limits](../README.md#source-overload).
- [Implementing SLOs](https://sre.google/workbook/implementing-slos/): Selecting indicators, targets, and the improvement process. [Access and technical limits](../README.md#source-slo).

[Back to Database Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

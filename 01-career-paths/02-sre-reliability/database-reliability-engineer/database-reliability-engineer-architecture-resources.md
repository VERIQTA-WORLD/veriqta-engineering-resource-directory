# Database Reliability Engineer: Architecture Resources

Database availability choices are also data choices: promotion, writer isolation, archive coverage, and application compatibility belong in the same review.

## Separate replication and backup goals

Replication can support availability or read distribution while backups support recovery to a different historical state. Consider corruption and operator mistakes that can propagate. Define recovery coverage for each failure class.

## Design authority during failover

Document who can promote, how routing changes, how writer conflict is prevented, and how old resources are reconciled. Include ambiguous network partitions. A new endpoint alone does not establish that only the intended writer can accept changes.

## Design the restore path end to end

Include archive continuity, keys, storage, database startup, application compatibility, and controlled traffic acceptance. Set recovery expectations using a data size and environment representative enough for the requirement. Retain a route for returning to normal operations.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [PostgreSQL: High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/high-availability.html): The comparison of approaches, then the applicable replication section. [Access and technical limits](../README.md#source-pg-ha).
- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html): Base backup prerequisites, archiving, and recovery configuration. [Access and technical limits](../README.md#source-pg-pitr).
- [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html): The relevant activity, replication, I/O, or database statistics views. [Access and technical limits](../README.md#source-pg-stats).
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html): Connection settings and their resource implications. [Access and technical limits](../README.md#source-pg-conn).

[Back to Database Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

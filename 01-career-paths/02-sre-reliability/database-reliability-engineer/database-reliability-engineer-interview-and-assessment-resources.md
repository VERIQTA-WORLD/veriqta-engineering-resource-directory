# Database Reliability Engineer: Interview and Assessment Resources

Explain which data and authority conditions make an action acceptable before proposing a failover or configuration change.

## Connections rise while useful throughput falls

Compare long transactions, lock waits, connection churn, application retries, and storage bottlenecks. Explain why increasing a connection limit might worsen the situation and which observations would justify an alternative.

## A lagging replica is proposed for promotion

Ask about the data-loss requirement, current replication state, writer isolation, and client routing. Explain which evidence is needed before promotion and how you would communicate unresolved loss risk.

## Recovery stops before the required point

Investigate base-backup suitability, WAL archive continuity, permissions, and target configuration. Explain how you would preserve the original evidence and avoid damaging the only usable recovery material.

## What to look for in your answer

Make data correctness and writer authority part of the recovery answer. Connection count, standby reachability, or a completed backup each leaves important questions unresolved.

## References for checking the reasoning

- [PostgreSQL: High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/high-availability.html) · [Access and technical limits](../README.md#source-pg-ha)
- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html) · [Access and technical limits](../README.md#source-pg-pitr)
- [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html) · [Access and technical limits](../README.md#source-pg-stats)

[Back to Database Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Database Reliability Engineer: Production Practice Resources

When connection counts rise and useful throughput falls, changing a server limit is only one possible intervention.

## Investigate pressure before changing limits

Correlate connection growth, long transactions, waits, storage pressure, replication behavior, and useful completions. Avoid assuming that a higher server limit fixes a queue. Preserve evidence and consider reducing admission or application concurrency when appropriate.

## Validate backups through restoration

Check backup completion and archive continuity, then perform authorized restore exercises into separate targets. Verify representative data and application behavior. Record access and timing dependencies so gaps lead to specific improvement work.

## Treat failover as a data decision

Use an agreed runbook with authority, replication observations, writer control, and routing checks. Verify data and client behavior after promotion. A failover can reduce downtime while creating freshness, consistency, or reconciliation consequences.

## Connection growth can be a symptom of waiting

Suppose useful database completions fall while active client connections rise. Applications respond to timeouts by opening more work, and one long transaction holds a resource other transactions need.

| Evidence | Interpretation to investigate |
| --- | --- |
| Many sessions wait behind the same operation | Blocking may constrain progress more than connection capacity |
| New attempts grow faster than useful completions | Retry or concurrency behavior may amplify pressure |
| Storage pressure grows with active work | The resource limit may move as more work is admitted |

Before increasing the connection limit, inspect waits, transaction duration, client behavior, and memory. Consider whether reducing admission or addressing the blocking work improves useful throughput. Preserve evidence and coordinate any transaction intervention with the workload owner.

## Operating references

- [PostgreSQL: High Availability, Load Balancing, and Replication](https://www.postgresql.org/docs/current/high-availability.html): The comparison of approaches, then the applicable replication section. [Access and technical limits](../README.md#source-pg-ha).
- [PostgreSQL: Continuous Archiving and Point-in-Time Recovery](https://www.postgresql.org/docs/current/continuous-archiving.html): Base backup prerequisites, archiving, and recovery configuration. [Access and technical limits](../README.md#source-pg-pitr).
- [PostgreSQL: Cumulative Statistics System](https://www.postgresql.org/docs/current/monitoring-stats.html): The relevant activity, replication, I/O, or database statistics views. [Access and technical limits](../README.md#source-pg-stats).
- [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html): Connection settings and their resource implications. [Access and technical limits](../README.md#source-pg-conn).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Database Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Scalability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for understanding how workload growth changes bottlenecks, coordination, resource demand, and service behavior. Match the installed version and actual configuration before interpreting an observation.

## What workload did the test generate?

Compare requested and achieved arrival behavior, data distribution, errors, and generator pressure.

Read [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/), starting with the test type matching your question, then its workload model. A load generator can become the bottleneck; validate the offered workload as well as the target.

## How does scaling respond to metrics?

Inspect supported metrics, control behavior, stabilization, readiness, and target limits.

Read [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/), starting with metrics, control behavior, readiness, and stabilization. Replica changes require downstream capacity and time to become useful; limits and dependencies still matter.

## What constrains client connections?

For PostgreSQL, inspect effective server settings alongside pooling and application concurrency.

Read [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html), starting with connection settings and their resource implications. More permitted connections do not necessarily provide more useful throughput; inspect memory and workload effects.

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

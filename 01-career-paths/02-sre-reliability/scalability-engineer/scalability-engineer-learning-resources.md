# Scalability Engineer: Learning Resources

Build a workload model before running a benchmark. Add scaling controls and shared-resource limits after you can explain which bottleneck the extra capacity is intended to relieve.

## Build a quantitative model

Read [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/), beginning with requirements, estimates, component capacity, and failure assumptions.

Estimate useful work, resource demand, data growth, and the expected first constraint. Keep assumptions visible.

## Design a workload-sensitive test

Read [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/), beginning with the test type matching your question, then its workload model.

Specify request mix, arrival behavior, key distribution, errors, and generator limits.

## Understand scaling delay

Read [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/), beginning with metrics, control behavior, readiness, and stabilization.

Trace the metrics and readiness path before new replicas contribute useful capacity.

## Check shared-resource limits

Read [PostgreSQL: Connections and Authentication](https://www.postgresql.org/docs/current/runtime-config-connection.html), beginning with connection settings and their resource implications.

Connect replica growth with application connection behavior and database pressure in a compatible PostgreSQL workload.

Choose a [project](scalability-engineer-labs-and-portfolio-projects.md) when you need execution evidence, or work through the [assessment scenarios](scalability-engineer-interview-and-assessment-resources.md) to apply the idea under changed conditions.

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

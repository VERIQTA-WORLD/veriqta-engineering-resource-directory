# Scalability Engineer: Labs and Portfolio Projects

## Locate the scaling limit

Compare a synthetic service at two controlled capacity levels under the same meaningful workload.

### Set up the exercise

Use an owned service, k6, target and generator telemetry, synthetic data, and strict load limits.

### Investigate the behavior

Keep the request mix constant, then introduce skew as a separate comparison. Inspect dependency work rather than counting replicas alone.

Retain achieved demand, useful throughput, errors, tail latency, resource use, and the explanation of the next bottleneck.

### Finish and clean up

Stop all generators and remove dedicated application and telemetry resources. Restore altered limits or scaling settings.

### References for this project

- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/) · [Prerequisites and limitations](../README.md#source-k6)
- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/) · [Prerequisites and limitations](../README.md#source-nasd)
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/) · [Prerequisites and limitations](../README.md#source-overload)

## Review a partitioning strategy

Design partitions for a growing multi-tenant workload with uneven access patterns.

### Set up the exercise

Use a spreadsheet or small local model with synthetic tenants, keys, data sizes, and operation counts.

### Investigate the behavior

Introduce a hot tenant and a larger working set. Compare repartitioning, admission controls, dedicated isolation, and migration effort.

Produce key-selection reasoning, skew observations, correctness requirements, rebalance steps, and expected operating costs.

### Finish and clean up

Remove optional model artifacts containing private data. Delete any dedicated cloud resources used for an extension.

### References for this project

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/) · [Prerequisites and limitations](../README.md#source-nasd)
- [Architecture Decision Records](https://adr.github.io/) · [Prerequisites and limitations](../README.md#source-adr)
- [FinOps Framework](https://www.finops.org/framework/) · [Prerequisites and limitations](../README.md#source-finops)

[Back to Scalability Engineer resources](README.md) · [Browse this career collection](../README.md)

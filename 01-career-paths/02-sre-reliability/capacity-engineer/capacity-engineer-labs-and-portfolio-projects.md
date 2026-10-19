# Capacity Engineer: Labs and Portfolio Projects

## Find the useful capacity envelope

Measure how a synthetic service behaves as demand increases, then identify the operating range that meets a stated latency and success requirement.

### Set up the exercise

Use an owned local service, k6, synthetic data, and independent target and generator observations. Define maximum load and test duration before starting.

### Investigate the behavior

Change one request class to do more work and compare queueing, errors, useful completions, and resource pressure. Stop at the agreed boundary.

Retain workload definition, request mix, achieved arrival behavior, latency distribution, errors, saturation observations, and the capacity recommendation.

### Finish and clean up

Stop the generator, restore lab settings, and remove dedicated application and telemetry resources. Check that scheduled or hosted runs have stopped.

### References for this project

- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/) · [Prerequisites and limitations](../README.md#source-k6)
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/) · [Prerequisites and limitations](../README.md#source-overload)
- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/) · [Prerequisites and limitations](../README.md#source-nasd)

## Review failure reserve

Build a design model for serving peak demand after losing one failure domain.

### Set up the exercise

Use a spreadsheet or script with synthetic values and clearly labeled assumptions. No infrastructure is required for the design exercise.

### Investigate the behavior

Reduce usable capacity unevenly rather than removing an equal fraction from every component. Include acquisition and warm-up delay.

Produce normal and degraded capacity ranges, the limiting resource, demand-management options, action thresholds, and cost consequences.

### Finish and clean up

Remove optional test resources if you extend the design into a lab. Preserve assumptions separately from measured results.

### References for this project

- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/) · [Prerequisites and limitations](../README.md#source-nasd)
- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) · [Prerequisites and limitations](../README.md#source-resources)
- [FinOps Framework](https://www.finops.org/framework/) · [Prerequisites and limitations](../README.md#source-finops)

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

# Capacity Engineer: Interview and Assessment Resources

Work through the demand, time window, limiting resource, and service objective before recommending more capacity.

## CPU is low but users wait

Explain which observations distinguish queued work, dependency saturation, lock contention, imbalanced routing, and slow request classes. Identify the denominator and time window before interpreting a resource average.

## A zone fails during the peak

Compare available capacity with the workload and latency requirement after one zone is lost. Explain placement imbalance, scale-up delay, quotas, and any demand-management decision. Do not infer failure capacity from total normal-state resource counts.

## A benchmark promises a large gain

Ask about request mix, data size, offered load, generator limits, errors, and tail latency. Explain which changes in workload would invalidate the reported gain and how you would validate the result for a different service.

## What to look for in your answer

Keep demand, useful completions, queueing, and generator behavior in the same explanation. Include the failure reserve and lead time behind a capacity recommendation rather than relying on average utilization.

## References for checking the reasoning

- [Kubernetes: Resource Management for Pods and Containers](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/) · [Access and technical limits](../README.md#source-resources)
- [Kubernetes: Horizontal Pod Autoscaling](https://kubernetes.io/docs/concepts/workloads/autoscaling/horizontal-pod-autoscale/) · [Access and technical limits](../README.md#source-hpa)
- [Grafana k6: Load test types](https://grafana.com/docs/k6/latest/testing-guides/test-types/) · [Access and technical limits](../README.md#source-k6)
- [Google SRE Workbook: Non-Abstract Large System Design](https://sre.google/workbook/non-abstract-design/) · [Access and technical limits](../README.md#source-nasd)
- [Google SRE: Handling Overload](https://sre.google/sre-book/handling-overload/) · [Access and technical limits](../README.md#source-overload)

[Back to Capacity Engineer resources](README.md) · [Browse this career collection](../README.md)

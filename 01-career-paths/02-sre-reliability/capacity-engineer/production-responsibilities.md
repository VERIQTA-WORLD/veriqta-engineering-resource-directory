# Capacity engineer: production responsibilities and operational resources

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Use the collections below to find guidance for concrete operating responsibilities. Agree owners, change authority, evidence, and escalation paths for the actual service; responsibilities differ across organizations.

## Browse this page

- [Build an evidence-based demand model](#build-an-evidence-based-demand-model)
- [Maintain expansion and failure headroom](#maintain-expansion-and-failure-headroom)
- [Investigate overload and regressions](#investigate-overload-and-regressions)
- [Review cost and capacity changes](#review-cost-and-capacity-changes)

## Build an evidence-based demand model

Record observed workload mix, peak rate, useful service capacity, bottlenecks, and uncertainty. Keep measurements reproducible across test runs.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [The USE method](https://www.brendangregg.com/usemethod.html) | Organize resource analysis around utilization, saturation, and errors. | Intermediate; public author reference. High utilization alone does not establish the limiting resource. |
| [k6 arrival-rate executors](https://grafana.com/docs/k6/latest/using-k6/scenarios/concepts/arrival-rate-vu-allocation/) | Understand workload generation and virtual-user allocation for arrival-rate tests. | Intermediate; public reference. Generator capacity and dropped iterations can distort the apparent system limit. |
| [k6 thresholds](https://grafana.com/docs/k6/latest/using-k6/thresholds/) | Define explicit load-test acceptance conditions rather than relying on a completed run. | Intermediate; public reference. Thresholds need a justified target, representative workload, and sufficient observations. |
| [Prometheus querying basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | Read query semantics before interpreting rates, ranges, and label-based aggregation. | Intermediate; public reference. Queries can omit traffic or combine unrelated services if labels are wrong. |
| [PostgreSQL statistics and activity](https://www.postgresql.org/docs/current/monitoring-stats.html) | Investigate sessions, activity, waits, and collected database statistics. | Intermediate; public reference. Visibility permissions and collection timing affect what you can conclude. |

## Maintain expansion and failure headroom

Review limits and time to useful capacity, including startup, placement, quota, and dependency constraints. Test assumptions used in the forecast.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |
| [Kubernetes horizontal pod autoscaling](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/) | Study metric-based workload scaling and controller behavior. | Intermediate; public reference. Scaling replicas does not necessarily resolve a dependency bottleneck or supply node capacity. |
| [Kubernetes Cluster Autoscaler](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler) | Review node-capacity scaling and provider integration constraints. | Advanced; public project repository. Provider quotas, node-group limits, and workload scheduling constraints affect expansion. |
| [Karpenter documentation](https://karpenter.sh/docs/) | Compare node provisioning and disruption behavior for supported Kubernetes environments. | Advanced; public project documentation. Provider compatibility, IAM permissions, quotas, and replacement effects require review. |
| [AWS Builders' Library: static stability](https://aws.amazon.com/builders-library/static-stability-using-availability-zones/) | Review designs that retain useful capacity during failures without depending on immediate expansion. | Advanced; public engineering article. AWS examples require workload-specific capacity and dependency analysis. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |

## Investigate overload and regressions

Correlate resource saturation with user impact and identify recovery actions that do not amplify the failure.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Effective troubleshooting](https://sre.google/sre-book/effective-troubleshooting/) | Use hypotheses and evidence to narrow a production failure rather than change unrelated settings. | Foundation onward; public chapter. Its method complements product-specific diagnostic references. |
| [Google SRE: handling overload](https://sre.google/sre-book/handling-overload/) | Study admission control, throttling, and overload behavior before increasing concurrency or capacity. | Intermediate; public book chapter. Google's implementations illustrate mechanisms, not settings to copy unchanged. |
| [Timeouts, retries, and backoff with jitter](https://d1.awsstatic.com/builderslibrary/pdfs/timeouts-retries-and-backoff-with-jitter.pdf) | Review dependency-call behavior and retry amplification risks. | Advanced; official PDF. Values require latency and failure evidence from your own system. |
| [Addressing cascading failures](https://sre.google/sre-book/addressing-cascading-failures/) | Review overload, feedback loops, and failure propagation. | Advanced; validate containment strategies with bounded tests and measurements. |
| [PostgreSQL EXPLAIN guidance](https://www.postgresql.org/docs/current/using-explain.html) | Read execution plans and investigate query behavior with documented planner concepts. | Intermediate; public guide. EXPLAIN ANALYZE executes the query; use controlled targets for statements with side effects. |
| [PostgreSQL explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html) | Understand lock conflicts and deadlock behavior before intervening in blocked database work. | Intermediate; public reference. Terminating a session can abort transactions and affect application behavior. |

## Review cost and capacity changes

Capture assumptions, observed results, and spending consequences. Include metrics storage, idle headroom, and recovery capacity in the review.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [FinOps Framework](https://www.finops.org/framework/) | Organize allocation, cost accountability, forecasting, and optimization responsibilities. | Intermediate; cost work requires billing and usage data, not estimates alone. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |
| [Infracost](https://www.infracost.io/docs/) | Evaluate infrastructure cost estimates in change-review workflows. | Intermediate; estimates depend on supported resources and usage assumptions, not actual billing guarantees. |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Review practical service-level objective design and adoption. | Intermediate; useful measures depend on service behavior and user expectations. |
| [Example error budget policy](https://sre.google/workbook/error-budget-policy/) | Find a concrete example of how reliability evidence can influence change decisions. | Intermediate; public appendix. A policy needs agreed authority, exceptions, and a measured service boundary. |
| [Managing incidents](https://sre.google/sre-book/managing-incidents/) | Review incident roles, coordination, communication, and operational response. | Intermediate; adapt role separation to team size and actual on-call arrangements. |
| [Postmortem culture](https://sre.google/sre-book/postmortem-culture/) | Review incident learning, documentation, and follow-up practices. | Intermediate; focus on evidenced contributing factors and actionable improvement. |

[Browse the other collections](README.md#resource-collections)

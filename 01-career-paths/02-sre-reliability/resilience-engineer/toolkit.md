# Resilience engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Failure experiment tools](#failure-experiment-tools)
- [Traffic and dependency controls](#traffic-and-dependency-controls)
- [Recovery and state tools](#recovery-and-state-tools)
- [Impact and recovery measurement](#impact-and-recovery-measurement)
- [Capacity and assessment aids](#capacity-and-assessment-aids)
- [Incident coordination options](#incident-coordination-options)

## Failure experiment tools

Choose an experiment mechanism for a specific failure assumption, target, and abort condition. Provider and Kubernetes tools have different permissions and supported actions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Chaos Toolkit documentation](https://chaostoolkit.org/) | Explore experiment definitions, drivers, and execution guidance for hypothesis-based failure testing. | Advanced; public project documentation. Extensions need separate review; experiments can affect availability and data. |
| [Chaos Mesh](https://chaos-mesh.org/docs/) | Explore Kubernetes failure-injection experiments. | Advanced; use isolated environments and bounded experiments before considering production use. |
| [LitmusChaos](https://docs.litmuschaos.io/) | Compare chaos experimentation and workflow capabilities. | Advanced; assess permissions, compatibility, failure scope, and recovery controls. |
| [AWS Fault Injection Service documentation](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html) | Review managed fault experiments, targets, actions, and operating controls. | Advanced; public documentation. AWS account permissions and charges apply; review stop conditions and each action's recovery behavior. |
| [Azure Chaos Studio Workspaces documentation (preview)](https://learn.microsoft.com/en-us/azure/chaos-studio/) | Evaluate Azure fault experiments and service-specific target requirements. | Intermediate to advanced; public documentation for a preview service. Check feature scope, supported targets, account requirements, and preview limitations before planning an experiment. |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |
| [stress-ng](https://github.com/ColinIanKing/stress-ng) | Explore controlled resource stressors for testing host and workload behavior. | Advanced; public project repository. Stressors can destabilize a host; use disposable environments and stop all stress processes afterward. |

## Traffic and dependency controls

Compare gateways, proxies, and meshes against the actual routing and isolation requirement. Check retry interaction and behavior when the control plane is unavailable.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |
| [HAProxy configuration manuals](https://docs.haproxy.org/) | Find versioned proxy, routing, health-check, and operational references. | Intermediate to advanced; public manual collection. Select the installed release and review connection, timeout, and retry interactions. |
| [NGINX documentation](https://nginx.org/en/docs/) | Review proxy, upstream, request processing, logging, and network configuration references. | Intermediate; public documentation. Open-source and commercial capabilities differ; select the correct product and version. |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Intermediate; APIs require a compatible implementation. Check conformance and feature status. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |
| [Flagger](https://docs.flagger.app/) | Explore automated progressive delivery with traffic-management and metric integrations. | Advanced; verify supported providers and analysis behavior for the chosen environment. |

## Recovery and state tools

Evaluate backup, restore, failover, and connection management separately. Recovery tools depend on usable data, credentials, storage, and a tested operating procedure.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [Patroni documentation](https://patroni.readthedocs.io/en/latest/) | Compare PostgreSQL high-availability orchestration and its distributed coordination dependencies. | Advanced; public project reference. Review fencing, datastore behavior, failover policy, and recovery; an orchestrator is not a backup. |
| [PgBouncer documentation](https://www.pgbouncer.org/config.html) | Compare connection pooling behavior, resource settings, and application compatibility. | Intermediate; public configuration reference. Pooling mode and session-dependent application features affect correctness. |
| [Redis Sentinel](https://redis.io/docs/latest/operate/oss_and_stack/management/sentinel/) | Review Redis monitoring and failover coordination in the documented Sentinel model. | Advanced; public reference. Clients, quorum arrangements, and network partitions affect failover outcomes. |
| [etcd documentation](https://etcd.io/docs/) | Review distributed coordination, maintenance, recovery, and failure behavior. | Advanced; public versioned reference collection. Quorum, disk latency, and recovery state need explicit operating plans. |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |

## Impact and recovery measurement

Observe user impact, dependency behavior, data outcomes, and time to useful service. Capture enough evidence to distinguish recovery from a temporary decline in demand.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Sloth](https://sloth.dev/) | Compare an SLO-to-Prometheus rule generator for service monitoring workflows. | Intermediate; public project documentation. Correct generated rules still require valid indicators and label boundaries. |
| [Pyrra](https://github.com/pyrra-dev/pyrra) | Evaluate SLO definition and visualization tooling around Prometheus-based measurements. | Intermediate; public project repository. Review deployment requirements and the service's actual measurement coverage. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Intermediate; instrumentation coverage and sampling affect what can be observed. |

## Capacity and assessment aids

Use load, scaling, and provider assessment tools to examine recovery capacity. An assessment is an input to validation rather than a completed resilience test.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |
| [KEDA documentation](https://keda.sh/docs/) | Evaluate event-driven workload autoscaling and its external metric dependencies. | Intermediate; public versioned project documentation. Scaling cannot repair slow dependencies or supply unavailable infrastructure capacity. |
| [Kubernetes Cluster Autoscaler](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler) | Review node-capacity scaling and provider integration constraints. | Advanced; public project repository. Provider quotas, node-group limits, and workload scheduling constraints affect expansion. |
| [Karpenter documentation](https://karpenter.sh/docs/) | Compare node provisioning and disruption behavior for supported Kubernetes environments. | Advanced; public project documentation. Provider compatibility, IAM permissions, quotas, and replacement effects require review. |
| [AWS Resilience Hub documentation](https://docs.aws.amazon.com/resilience-hub/) | Compare documented application-resilience assessment and operational recommendations. | Advanced; public reference. Service assessment is not proof of exercised workload recovery; AWS permissions and charges require review. |
| [AWS Service Quotas documentation](https://docs.aws.amazon.com/servicequotas/) | Investigate account and service limits that can block provisioning or scaling. | Intermediate; public documentation. Quota increases are not guaranteed and may not resolve regional resource scarcity. |
| [OpenCost](https://opencost.io/docs/) | Explore Kubernetes cost allocation and cost visibility. | Intermediate; allocation assumptions, data quality, and shared costs need review. |

## Incident coordination options

Compare incident workflows, ownership, escalation, and integration requirements. These hosted tools support coordination; they do not replace service objectives, diagnosis, or an agreed response process.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PagerDuty incident documentation](https://support.pagerduty.com/main/docs/incidents) | Inspect incident states, ownership, response, and notification behavior in a hosted incident platform. | Intermediate; public vendor documentation. Using the platform requires an account and suitable service access; review schedules, integrations, escalation, and feature availability. |
| [incident.io help center](https://docs.incident.io/) | Compare a hosted platform's incident response, on-call, alerting, and workflow documentation. | Intermediate; public vendor help center. Platform use requires an account and appropriate access; select direct guides and check integration and product boundaries. |

[Browse the other collections](README.md#resource-collections)

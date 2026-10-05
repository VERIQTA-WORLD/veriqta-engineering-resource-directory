# Service reliability engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Service signals and diagnostics](#service-signals-and-diagnostics)
- [Objectives and incident signals](#objectives-and-incident-signals)
- [Release, configuration, and policy](#release-configuration-and-policy)
- [Traffic, identity, and data dependencies](#traffic-identity-and-data-dependencies)
- [Test, fault, and capacity tools](#test-fault-and-capacity-tools)
- [Provider monitoring options](#provider-monitoring-options)
- [Incident coordination options](#incident-coordination-options)

## Service signals and diagnostics

Select metrics, traces, logs, probes, and profiles around the service outcome and dependency questions. Plan sensitive-data handling and collection overhead.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Parca documentation](https://www.parca.dev/docs/overview/) | Explore continuous profiling for investigating resource consumption over time. | Advanced; public project documentation. Collection permissions, symbolization, and profile storage need review. |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. The linked manual currently displays development version 4.7.4; match the installed release. |

## Objectives and incident signals

Compare objective definitions, recording rules, alert evaluation, and routing. Check how missing data or telemetry failure affects the user's service signal.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Sloth](https://sloth.dev/) | Compare an SLO-to-Prometheus rule generator for service monitoring workflows. | Intermediate; public project documentation. Correct generated rules still require valid indicators and label boundaries. |
| [Pyrra](https://github.com/pyrra-dev/pyrra) | Evaluate SLO definition and visualization tooling around Prometheus-based measurements. | Intermediate; public project repository. Review deployment requirements and the service's actual measurement coverage. |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Prometheus recording rules](https://prometheus.io/docs/prometheus/latest/configuration/recording_rules/) | Plan reusable query results and rule evaluation for operational dashboards and alerts. | Intermediate; public reference. Rule evaluation load and failure visibility require operational review. |
| [Prometheus alerting rules](https://prometheus.io/docs/prometheus/latest/configuration/alerting_rules/) | Define actionable alert conditions and understand their evaluation behavior. | Intermediate; public reference. Alert expressions need routing, ownership, and diagnostic context. |
| [Prometheus rule unit tests](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/) | Test rule behavior against synthetic time-series inputs before changing production alerts. | Intermediate; public practical reference. Synthetic series do not establish live scrape or routing correctness. |

## Release, configuration, and policy

Match the delivery mechanism to the service and infrastructure ownership model. Review rollback, credential boundaries, and artifact evidence alongside deployment progress.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | Compare application synchronization, repository integration, and Kubernetes deployment management. | Intermediate; define repository and cluster trust boundaries, controller availability, and recovery. |
| [Flux](https://fluxcd.io/flux/) | Evaluate controller-based GitOps reconciliation for Kubernetes sources and workloads. | Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |
| [Flagger](https://docs.flagger.app/) | Explore automated progressive delivery with traffic-management and metric integrations. | Advanced; verify supported providers and analysis behavior for the chosen environment. |
| [GitHub Actions](https://docs.github.com/en/actions) | Design repository workflows, reusable automation, environments, and runner arrangements. | Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions. |
| [GitLab CI/CD](https://docs.gitlab.com/ci/) | Compare pipeline configuration, runners, artifacts, and delivery integration within GitLab. | Intermediate; distinguish hosted and self-managed responsibilities and feature tiers. |
| [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) | Assess pipeline-as-code and extensibility for an operated automation service. | Intermediate; controller, agents, plugins, credentials, upgrades, and backups require ownership. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Kustomize](https://kubectl.docs.kubernetes.io/references/kustomize/) | Compose and customize Kubernetes manifests without a chart template language. | Intermediate; evaluate overlay sprawl and compatibility with the version embedded in your tooling. |
| [Open Policy Agent](https://www.openpolicyagent.org/docs/) | Evaluate general policy evaluation and integration patterns. | Advanced; the integrating system must enforce the decision. Test policy and failure behavior. |
| [Kyverno](https://kyverno.io/docs/) | Assess Kubernetes policy validation, mutation, and other documented policy capabilities. | Intermediate; evaluate admission availability, exceptions, enforcement mode, and policy tests. |
| [Sigstore Cosign](https://docs.sigstore.dev/cosign/signing/overview/) | Design artifact signing and verification workflows. | Advanced; define trusted identities, verification policy, and failure handling. A signature does not prove software quality. |

## Traffic, identity, and data dependencies

Review gateway, proxy, identity, secret, database, and connection behavior as part of the service's dependency map.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |
| [HAProxy configuration manuals](https://docs.haproxy.org/) | Find versioned proxy, routing, health-check, and operational references. | Intermediate to advanced; public manual collection. Select the installed release and review connection, timeout, and retry interactions. |
| [NGINX documentation](https://nginx.org/en/docs/) | Review proxy, upstream, request processing, logging, and network configuration references. | Intermediate; public documentation. Open-source and commercial capabilities differ; select the correct product and version. |
| [Kubernetes Gateway API](https://github.com/kubernetes-sigs/gateway-api) | Compare Kubernetes traffic-routing APIs and implementation support. | Intermediate; APIs require a compatible implementation. Check conformance and feature status. |
| [Keycloak](https://www.keycloak.org/documentation) | Evaluate identity and access-management capabilities for platform applications. | Advanced; integration, federation, sessions, availability, and upgrades require specialist review. |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [External Secrets Operator](https://external-secrets.io/latest/) | Evaluate synchronization between external secret stores and Kubernetes. | Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets. |
| [PostgreSQL documentation](https://www.postgresql.org/docs/current/) | Locate administration, SQL, replication, security, and operating references for PostgreSQL. | Foundation onward; public documentation. The current alias tracks a changing major version; use the manual for the installed server. |
| [Redis documentation](https://redis.io/docs/latest/) | Find command, deployment, persistence, replication, and operating references for Redis products. | Foundation onward; public documentation. Distinguish product editions and deployment models; review applicable terms separately. |
| [PgBouncer documentation](https://www.pgbouncer.org/config.html) | Compare connection pooling behavior, resource settings, and application compatibility. | Intermediate; public configuration reference. Pooling mode and session-dependent application features affect correctness. |

## Test, fault, and capacity tools

Use functional, integration, load, and failure tests for explicit questions. Test-container and local-cluster resources do not reproduce all production failure conditions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [pytest](https://docs.pytest.org/en/stable/) | Test Python automation with fixtures, assertions, parametrization, and temporary environments. | Intermediate; public project documentation. Mocks cannot establish that a live provider behaves correctly. |
| [Testcontainers](https://testcontainers.com/guides/) | Find guides for container-backed integration test dependencies. | Intermediate; runtime and language-library requirements vary. Tests still need meaningful assertions. |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |
| [Chaos Toolkit documentation](https://chaostoolkit.org/) | Explore experiment definitions, drivers, and execution guidance for hypothesis-based failure testing. | Advanced; public project documentation. Extensions need separate review; experiments can affect availability and data. |
| [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) | Create a local Kubernetes environment for manifest and controller experiments. | Intermediate; requires a supported container environment. Review host capacity and cluster deletion instructions. |
| [minikube start guide](https://minikube.sigs.k8s.io/docs/start/) | Explore a local Kubernetes setup and supported driver choices. | Foundation to intermediate; driver and operating-system prerequisites vary. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. |

## Provider monitoring options

Compare provider-native collection and alerting with your service instrumentation. Choose the relevant provider; public documentation and service operation have different access and cost conditions.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Amazon CloudWatch documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html) | Find AWS monitoring, alarms, logs, service signals, and collection references for workload investigation. | Intermediate; public provider documentation. An AWS account and relevant permissions are needed to operate the service; collection, retention, and features have separate billing conditions. |
| [Azure Monitor overview](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview) | Review Azure's monitoring components and links for application and infrastructure observation. | Intermediate; public provider overview. Check the selected component's data collection, identity, retention, and charging model before deployment. |
| [Google Cloud Monitoring overview](https://cloud.google.com/monitoring/docs/monitoring-overview) | Find Google Cloud metric collection, dashboards, alerting, and monitoring integration references. | Intermediate; public provider documentation. Operating access requires appropriate project permissions; telemetry volume and selected services affect charges. |

## Incident coordination options

Compare incident workflows, ownership, escalation, and integration requirements. These hosted tools support coordination; they do not replace service objectives, diagnosis, or an agreed response process.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [PagerDuty incident documentation](https://support.pagerduty.com/main/docs/incidents) | Inspect incident states, ownership, response, and notification behavior in a hosted incident platform. | Intermediate; public vendor documentation. Using the platform requires an account and suitable service access; review schedules, integrations, escalation, and feature availability. |
| [incident.io help center](https://docs.incident.io/) | Compare a hosted platform's incident response, on-call, alerting, and workflow documentation. | Intermediate; public vendor help center. Platform use requires an account and appropriate access; select direct guides and check integration and product boundaries. |

[Browse the other collections](README.md#resource-collections)

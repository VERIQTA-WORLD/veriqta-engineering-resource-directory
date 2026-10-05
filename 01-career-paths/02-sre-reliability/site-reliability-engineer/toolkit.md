# Site reliability engineer: tool directory

[Career overview](README.md) · [SRE and reliability directory](../README.md)

Compare tools by the engineering task, execution environment, integration boundaries, and operating effort. Public documentation access does not establish that hosted services, licenses, or infrastructure use are free.

## Browse this page

- [Observation and diagnosis](#observation-and-diagnosis)
- [Objectives, alerts, and telemetry backends](#objectives-alerts-and-telemetry-backends)
- [Automation and safe delivery](#automation-and-safe-delivery)
- [Capacity, fault, and recovery tools](#capacity-fault-and-recovery-tools)
- [Runtime and dependency foundations](#runtime-and-dependency-foundations)
- [Provider monitoring options](#provider-monitoring-options)
- [Incident coordination options](#incident-coordination-options)
- [Delegated operational jobs](#delegated-operational-jobs)

## Observation and diagnosis

Choose signal types around concrete service questions. Include user-facing probes, resource measurements, tracing, and profiles without assuming every service needs the same telemetry stack.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Prometheus](https://prometheus.io/docs/introduction/overview/) | Evaluate metrics collection, querying, and monitoring architecture. | Intermediate; plan label cardinality, retention, storage, and availability. |
| [Grafana](https://grafana.com/docs/grafana/latest/) | Build and govern dashboards and documented observability integrations. | Intermediate; distinguish the operated software from cloud services and edition-specific capabilities. |
| [OpenTelemetry](https://opentelemetry.io/docs/) | Plan instrumentation, telemetry collection, and export across system components. | Intermediate; select signal pipelines and backends deliberately. Review data sensitivity and collector capacity. |
| [Jaeger](https://www.jaegertracing.io/docs/) | Review distributed tracing components and deployment guidance. | Intermediate; instrumentation coverage and sampling affect what can be observed. |
| [Grafana Loki](https://grafana.com/docs/loki/latest/) | Evaluate log aggregation, storage, queries, and deployment approaches. | Advanced; ingestion volume, label design, retention, and tenancy affect cost and performance. |
| [Prometheus Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) | Probe selected network and service endpoints from an external observation point. | Intermediate; public project repository. Probe location, credentials, and traffic volume change what results mean. |
| [Prometheus Node Exporter](https://github.com/prometheus/node_exporter) | Collect host metrics for resource pressure and infrastructure monitoring. | Intermediate; public project repository. Review enabled collectors, privileges, and host access boundaries. |
| [kube-state-metrics](https://github.com/kubernetes/kube-state-metrics) | Observe Kubernetes object state alongside workload and node performance metrics. | Intermediate; public project repository. Object-state metrics do not replace application-level service indicators. |
| [Parca documentation](https://www.parca.dev/docs/overview/) | Explore continuous profiling for investigating resource consumption over time. | Advanced; public project documentation. Collection permissions, symbolization, and profile storage need review. |
| [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) | Inspect capture and protocol-analysis workflows for network diagnosis. | Intermediate; capture only with authorization. Traffic may contain sensitive data and encrypted payloads may remain unreadable. The linked manual currently displays development version 4.7.4; match the installed release. |

## Objectives, alerts, and telemetry backends

Compare SLO representation, alert evaluation, routing, and backend requirements. Cardinality, retention, and missing data can affect both cost and operational usefulness.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Sloth](https://sloth.dev/) | Compare an SLO-to-Prometheus rule generator for service monitoring workflows. | Intermediate; public project documentation. Correct generated rules still require valid indicators and label boundaries. |
| [Pyrra](https://github.com/pyrra-dev/pyrra) | Evaluate SLO definition and visualization tooling around Prometheus-based measurements. | Intermediate; public project repository. Review deployment requirements and the service's actual measurement coverage. |
| [OpenSLO](https://openslo.com/) | Review a shared specification for expressing service-level objectives and related metadata. | Intermediate; public specification project. Implementation support and supported schema versions vary. |
| [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) | Design alert grouping, routing, inhibition, and notification integration. | Intermediate; routing does not establish that an alert is actionable. Test ownership and delivery. |
| [Prometheus rule unit tests](https://prometheus.io/docs/prometheus/latest/configuration/unit_testing_rules/) | Test rule behavior against synthetic time-series inputs before changing production alerts. | Intermediate; public practical reference. Synthetic series do not establish live scrape or routing correctness. |
| [Thanos documentation](https://thanos.io/tip/thanos/getting-started.md/) | Compare a distributed metrics architecture and its component responsibilities. | Advanced; public project guide. The tip documentation can describe development features; select a matching release. |
| [VictoriaMetrics documentation](https://docs.victoriametrics.com/) | Compare documented metrics ingestion, querying, deployment, and operation options. | Intermediate to advanced; public reference collection. Distinguish single-node, cluster, and commercial feature boundaries. |
| [Prometheus storage](https://prometheus.io/docs/prometheus/latest/storage/) | Review retention, local storage, and durability considerations for metrics infrastructure. | Advanced; public reference. Persistent storage is not a substitute for monitoring continuity or an exercised restore. |

## Automation and safe delivery

Use tools that fit the service ownership model and provide reviewable, testable changes. Scripts, infrastructure engines, and controllers require different handling of state and failure.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Python tutorial](https://docs.python.org/3/tutorial/) | Read the language tutorial before maintaining automation that parses data, calls services, or manages files. | Foundation in Python; assumes basic programming knowledge. Publicly readable; use an isolated virtual environment and match the installed interpreter. |
| [pytest](https://docs.pytest.org/en/stable/) | Test Python automation with fixtures, assertions, parametrization, and temporary environments. | Intermediate; public project documentation. Mocks cannot establish that a live provider behaves correctly. |
| [jq manual](https://jqlang.org/manual/) | Inspect and transform JSON returned by command-line clients and infrastructure APIs. | Foundation onward; publicly readable manual. Validate missing fields rather than assuming one provider response shape. |
| [Mike Farah yq](https://mikefarah.gitbook.io/yq/) | Read and update structured configuration with the documented yq implementation. | Intermediate; public documentation. Several unrelated utilities share the name yq; check the actual implementation. |
| [Ansible playbooks](https://docs.ansible.com/ansible/latest/playbook_guide/index.html) | Plan configuration automation, orchestration, and reusable operational tasks. | Intermediate; idempotency depends on modules and task design. Check collection and target compatibility. |
| [Terraform](https://developer.hashicorp.com/terraform/docs) | Assess declarative provisioning, providers, state, and reusable configuration. | Intermediate; review backend protection and provider behavior. Product edition and license terms need separate review. |
| [OpenTofu](https://opentofu.org/docs/) | Evaluate declarative infrastructure provisioning and its documented state and workflow features. | Intermediate; verify provider, module, and state compatibility for your migration instead of assuming interchangeability. |
| [Pulumi IaC](https://www.pulumi.com/docs/iac/) | Compare infrastructure expressed through supported programming languages and SDKs. | Intermediate; consider language runtime, state backend, secret handling, and hosted-service dependencies. |
| [Argo CD](https://argo-cd.readthedocs.io/en/stable/) | Compare application synchronization, repository integration, and Kubernetes deployment management. | Intermediate; define repository and cluster trust boundaries, controller availability, and recovery. |
| [Flux](https://fluxcd.io/flux/) | Evaluate controller-based GitOps reconciliation for Kubernetes sources and workloads. | Intermediate; design source permissions, reconciliation ownership, bootstrap, and recovery. |
| [Argo Rollouts](https://argo-rollouts.readthedocs.io/en/stable/) | Assess canary and blue-green rollout controls and analysis integration. | Advanced; traffic routing and metrics integrations determine what a rollout can actually verify. |
| [Flagger](https://docs.flagger.app/) | Explore automated progressive delivery with traffic-management and metric integrations. | Advanced; verify supported providers and analysis behavior for the chosen environment. |
| [GitHub Actions](https://docs.github.com/en/actions) | Design repository workflows, reusable automation, environments, and runner arrangements. | Intermediate; hosted usage and enterprise features depend on account and plan. Evaluate permissions and third-party actions. |
| [GitLab CI/CD](https://docs.gitlab.com/ci/) | Compare pipeline configuration, runners, artifacts, and delivery integration within GitLab. | Intermediate; distinguish hosted and self-managed responsibilities and feature tiers. |
| [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) | Assess pipeline-as-code and extensibility for an operated automation service. | Intermediate; controller, agents, plugins, credentials, upgrades, and backups require ownership. |

## Capacity, fault, and recovery tools

Select tests and recovery tools for explicit assumptions about load, dependencies, state, and platform failure. Keep destructive effects confined to the authorized target.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Grafana k6](https://grafana.com/docs/k6/latest/) | Evaluate programmable load and performance testing. | Intermediate; model real traffic and service objectives. External targets need explicit test authorization. |
| [Locust](https://docs.locust.io/en/stable/) | Assess Python-based load modeling and distributed test execution. | Intermediate; confirm the documentation release, because moving branches can expose development builds. Workload design and load-generator limits affect conclusions. |
| [PostgreSQL pgbench](https://www.postgresql.org/docs/current/pgbench.html) | Explore database workload generation and benchmark interpretation in a disposable database. | Intermediate; public CLI guide. Initialization and workloads modify data and can saturate the server; remove the test database when finished. |
| [Toxiproxy](https://github.com/Shopify/toxiproxy) | Introduce controlled connection faults between a test client and service. | Intermediate; public project repository and examples. Confine the proxy to authorized test traffic and remove injected faults afterward. |
| [Chaos Toolkit documentation](https://chaostoolkit.org/) | Explore experiment definitions, drivers, and execution guidance for hypothesis-based failure testing. | Advanced; public project documentation. Extensions need separate review; experiments can affect availability and data. |
| [Chaos Mesh](https://chaos-mesh.org/docs/) | Explore Kubernetes failure-injection experiments. | Advanced; use isolated environments and bounded experiments before considering production use. |
| [LitmusChaos](https://docs.litmuschaos.io/) | Compare chaos experimentation and workflow capabilities. | Advanced; assess permissions, compatibility, failure scope, and recovery controls. |
| [Velero](https://velero.io/docs/) | Review Kubernetes backup, restore, and migration workflows. | Advanced; validate storage-provider support and application consistency. A completed backup is not a proven restore. |
| [pgBackRest user guide](https://pgbackrest.org/user-guide.html) | Review PostgreSQL backup, archive, restore, and repository workflows. | Advanced; public project guide. Secure backup credentials and validate restores with the matching database version. |
| [Patroni documentation](https://patroni.readthedocs.io/en/latest/) | Compare PostgreSQL high-availability orchestration and its distributed coordination dependencies. | Advanced; public project reference. Review fencing, datastore behavior, failover policy, and recovery; an orchestrator is not a backup. |

## Runtime and dependency foundations

Use implementation-specific tools and references for container, network, identity, data, and secret dependencies. Availability of the service can depend on any of these layers.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Kubernetes](https://kubernetes.io/docs/) | Evaluate workload scheduling, APIs, service discovery, configuration, and cluster operations. | Intermediate to advanced; application and cluster operating knowledge are prerequisites for architecture decisions. |
| [Docker documentation](https://docs.docker.com/) | Explore image construction, container workflows, and available Docker products. | Foundation onward; distinguish Engine, Desktop, and hosted products. Review applicable subscription terms. |
| [Helm](https://helm.sh/docs/) | Package and distribute Kubernetes applications through charts and releases. | Intermediate; assess chart provenance, rendered permissions, upgrade behavior, and release ownership. |
| [Cilium](https://docs.cilium.io/en/stable/) | Review networking, network policy, and observability capabilities for supported environments. | Advanced; assess kernel, platform, deployment, and upgrade prerequisites. |
| [Envoy](https://www.envoyproxy.io/docs/envoy/latest/) | Review proxy capabilities, configuration, and control-plane integration. | Advanced; latest documentation may cover development builds. Select the deployed release and define configuration, certificate, and upgrade ownership. |
| [Istio](https://istio.io/latest/docs/) | Assess service-mesh traffic management, identity, security, and telemetry guidance. | Advanced; evaluate supported data-plane modes, operational complexity, and application impact. |
| [HashiCorp Vault](https://developer.hashicorp.com/vault/docs) | Compare centralized secrets, authentication methods, and secret-engine capabilities. | Advanced; sealing, recovery, access control, audit, and edition-specific features require design. |
| [External Secrets Operator](https://external-secrets.io/latest/) | Evaluate synchronization between external secret stores and Kubernetes. | Intermediate; assess provider identity, refresh behavior, and exposure in Kubernetes Secrets. |
| [Keycloak](https://www.keycloak.org/documentation) | Evaluate identity and access-management capabilities for platform applications. | Advanced; integration, federation, sessions, availability, and upgrades require specialist review. |
| [PostgreSQL documentation](https://www.postgresql.org/docs/current/) | Locate administration, SQL, replication, security, and operating references for PostgreSQL. | Foundation onward; public documentation. The current alias tracks a changing major version; use the manual for the installed server. |
| [Redis documentation](https://redis.io/docs/latest/) | Find command, deployment, persistence, replication, and operating references for Redis products. | Foundation onward; public documentation. Distinguish product editions and deployment models; review applicable terms separately. |
| [PgBouncer documentation](https://www.pgbouncer.org/config.html) | Compare connection pooling behavior, resource settings, and application compatibility. | Intermediate; public configuration reference. Pooling mode and session-dependent application features affect correctness. |

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

## Delegated operational jobs

Compare job execution with scripts and controllers around target scope, credential handling, permissions, repeatability, and execution records.

| Resource | What it helps with | Level, access, and selection notes |
| --- | --- | --- |
| [Rundeck user guide](https://docs.rundeck.com/docs/manual/) | Review projects, jobs, execution, and access control for repeatable operational workflows. | Intermediate; public product documentation. Distinguish community and commercial capabilities; delegated job execution needs credential and target boundaries. |

[Browse the other collections](README.md#resource-collections)

# Observability Engineering

Choose a question before choosing a dashboard: which requests failed, where time was spent, which dependency changed, or what requires an operator response?

<table>
<tr>
<td align="center"><a href="https://opentelemetry.io/docs/concepts/signals/"><img src="../assets/logos/opentelemetry.svg" width="48" height="48" alt="OpenTelemetry"/><br/>OpenTelemetry</a></td>
<td align="center"><a href="https://prometheus.io/docs/introduction/overview/"><img src="../assets/logos/prometheus.svg" width="48" height="48" alt="Prometheus"/><br/>Prometheus</a></td>
<td align="center"><a href="https://grafana.com/docs/grafana/latest/fundamentals/"><img src="../assets/logos/grafana.svg" width="48" height="48" alt="Grafana"/><br/>Grafana</a></td>
</tr>
</table>

## Pick the resource that answers it

**[OpenTelemetry signals →](https://opentelemetry.io/docs/concepts/signals/)**  
Understand the roles of telemetry signals before deciding what to instrument.  
**Free documentation · Foundation to intermediate**

**[Prometheus overview →](https://prometheus.io/docs/introduction/overview/)**  
Learn its metrics model and components before moving into queries and alert rules.  
**Free documentation · Basic service-operation knowledge helpful**

**[Grafana fundamentals →](https://grafana.com/docs/grafana/latest/fundamentals/)**  
Find introductory material for data sources, querying, and dashboards.  
**Free documentation · Product access and hosting conditions vary**

## Check the quality of the evidence

Before adding another dashboard, check whether your signals can be related to the same service, environment, and time window. Missing context can make individually useful logs, metrics, and traces difficult to compare.

Choose one investigation question and collect only what helps answer it. Review retention, sensitive fields, and the cost of growing telemetry volume as you expand instrumentation.

## Follow a slow request

Use the [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) and its [Docker deployment instructions](https://opentelemetry.io/docs/demo/docker-deployment/) to explore an instrumented application. Check current CPU, memory, Docker, and Compose requirements first; this is a multi-service demo. Documentation is free, and running it uses your infrastructure.

Find a request in a trace, identify a slow span, and compare the trace with the relevant service metrics and logs. Write down what each signal establishes and what remains uncertain. A dashboard image without the investigation question explains little.

Follow the demo’s shutdown instructions, remove exercise storage you no longer need, and check for any hosted telemetry destinations you configured.

When you need to turn the evidence into release or response decisions, continue to [SRE](sre.md). For cluster-specific investigation, open [Kubernetes engineering](kubernetes-engineering.md).

[All career paths](README.md) · [Directory homepage](../README.md)

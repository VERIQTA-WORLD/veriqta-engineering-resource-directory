# Observability Engineering

Choose a question before choosing a dashboard: which requests failed, where time was spent, which dependency changed, or what requires an operator response?

<table>
<tr>
<td align="center"><a href="../04-tools/opentelemetry.md"><img src="../assets/logos/opentelemetry.svg" width="48" height="48" alt="OpenTelemetry"/><br/>OpenTelemetry</a></td>
<td align="center"><a href="../04-tools/prometheus.md"><img src="../assets/logos/prometheus.svg" width="48" height="48" alt="Prometheus"/><br/>Prometheus</a></td>
<td align="center"><a href="../04-tools/grafana.md"><img src="../assets/logos/grafana.svg" width="48" height="48" alt="Grafana"/><br/>Grafana</a></td>
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

## Keep the responsibilities distinct

| You need to… | Follow |
| --- | --- |
| Instrument and correlate application behavior | [OpenTelemetry resources](../04-tools/opentelemetry.md) |
| Work with metrics and alert-rule references | [Prometheus resources](../04-tools/prometheus.md) |
| Explore and present data | [Grafana resources](../04-tools/grafana.md) |
| Connect signals to a service objective | [Reliability topics](../03-topics/reliability.md) |

## Follow one request

Instrument a synthetic application and connect one request to its relevant signals. Introduce a bounded delay or error, then explain which observation helped locate it. Exclude secrets and personal data from telemetry. After practice, stop collectors and test workloads and remove temporary storage or hosted resources you no longer need.

[Explore projects →](../06-practice/projects.md) · [Observability topics →](../03-topics/observability.md)

When you need to turn the evidence into release or response decisions, continue to [SRE](sre.md). For cluster-specific investigation, open [Kubernetes engineering](kubernetes-engineering.md).

[All career paths](README.md) · [Directory homepage](../README.md)

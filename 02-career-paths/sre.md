# Site Reliability Engineering

Choose resources that help you understand user impact, respond to failures, and reduce recurring operational work. If you are new to running applications, begin with [Linux and systems](linux-systems.md).

## Read for the problem you have

| Your question | Start with | Access |
| --- | --- | --- |
| What should service reliability measure? | [Implementing SLOs](https://sre.google/workbook/implementing-slos/) — connect objectives to useful service behavior | Free online chapter |
| Which failures should wake someone up? | [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) — compare alerting approaches and their trade-offs | Free online chapter |
| What should you study next? | [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) — select chapters on releases, incidents, or your current concern | Free online book |

These readings assume some familiarity with operating services. Adapt the examples to your workload and team.

## What this path adds

You turn service behavior into decisions about releases, response, and engineering priorities. If your immediate task is instrumentation or signal correlation, use [observability](observability.md) first. If you already collect useful data, start with the SLO and alerting chapters above.

## Know what each signal is for

<table>
<tr>
<td align="center"><a href="https://prometheus.io/docs/introduction/overview/"><img src="../assets/logos/prometheus.svg" width="48" height="48" alt="Prometheus"/><br/>Prometheus</a></td>
<td align="center"><a href="https://grafana.com/docs/grafana/latest/fundamentals/"><img src="../assets/logos/grafana.svg" width="48" height="48" alt="Grafana"/><br/>Grafana</a></td>
<td align="center"><a href="https://opentelemetry.io/docs/concepts/signals/"><img src="../assets/logos/opentelemetry.svg" width="48" height="48" alt="OpenTelemetry"/><br/>OpenTelemetry</a></td>
</tr>
</table>

Metrics help quantify behavior; traces and logs help investigate particular requests. Choose signals from the service question, then choose the tools that can supply them.

## Turn a reliability target into a decision

Use [Implementing SLOs](https://sre.google/workbook/implementing-slos/) to define a successful request and a measurement window for a small service. Then follow [Prometheus Getting Started](https://prometheus.io/docs/prometheus/latest/getting_started/) to learn collection and querying. The guide needs a local Prometheus installation; reading is free.

Your result should show the objective, measured good and total events, and what action you would take if reliability worsened. Explain how missing telemetry differs from a healthy service. Remove the local server and temporary data after practice.

If you already handle incidents, skip the introductory collection work and compare your alert policy with [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/). Look for alerts that demand attention without identifying a useful response.

## Follow the next question

If shared developer services keep failing, explore [platform engineering](platform-engineering.md). For releases and automation, use [DevOps](devops.md).

[All career paths](README.md) · [Directory homepage](../README.md)

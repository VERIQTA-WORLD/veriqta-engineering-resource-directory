# Site Reliability Engineering

Choose resources that help you understand user impact, respond to failures, and reduce recurring operational work. If you are new to running applications, begin with [Linux and systems](linux-systems.md).

## Read for the problem you have

| Your question | Start with | Access |
| --- | --- | --- |
| What should service reliability measure? | [Implementing SLOs](https://sre.google/workbook/implementing-slos/) — connect objectives to useful service behavior | Free online chapter |
| Which failures should wake someone up? | [Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/) — compare alerting approaches and their trade-offs | Free online chapter |
| What should you study next? | [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) — select chapters on releases, incidents, or your current concern | Free online book |

These readings assume some familiarity with operating services. Adapt the examples to your workload and team.

## Know what each signal is for

<table>
<tr>
<td align="center"><a href="../04-tools/prometheus.md"><img src="../assets/logos/prometheus.svg" width="48" height="48" alt="Prometheus"/><br/>Prometheus</a></td>
<td align="center"><a href="../04-tools/grafana.md"><img src="../assets/logos/grafana.svg" width="48" height="48" alt="Grafana"/><br/>Grafana</a></td>
<td align="center"><a href="../04-tools/opentelemetry.md"><img src="../assets/logos/opentelemetry.svg" width="48" height="48" alt="OpenTelemetry"/><br/>OpenTelemetry</a></td>
</tr>
</table>


- [Prometheus](../04-tools/prometheus.md): find metrics and alert-rule resources.
- [Grafana](../04-tools/grafana.md): explore dashboards and investigation views.
- [OpenTelemetry](../04-tools/opentelemetry.md): understand instrumentation and request-level signals.

## Practise a reliability decision

Choose one user action in a disposable application. Define success, collect an appropriate signal, and introduce a bounded misconfiguration. Explain how you detected the failure and verified recovery. Use synthetic traffic and remove temporary monitoring resources after the exercise.

[Reliability topics](../03-topics/reliability.md) · [Challenges](../06-practice/challenges.md) · [Troubleshooting](../07-troubleshooting/)

## Follow the next question

If the measurement itself is unclear, open [observability](observability.md). If shared developer services keep failing, explore [platform engineering](platform-engineering.md). For releases and automation, use [DevOps](devops.md).

[All career paths](README.md) · [Directory homepage](../README.md)

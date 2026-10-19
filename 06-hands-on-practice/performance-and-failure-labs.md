# Performance and Failure Labs

Begin with a hypothesis, a small load or fault, and an explicit stop condition.

## Find the experiment reference

| Open | What you can find | Access |
| --- | --- | --- |
| [Systems Performance](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) | Brendan Gregg; study how to frame and investigate performance questions across a system. | Paid book; author material |
| [Brendan Gregg: Learning Linux performance](https://www.brendangregg.com/linuxperf.html) | Choose a performance method, visualization, or lecture around a question you can measure. | Free author material; linked books separate |
| [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/) | Explore an instrumented application and its signals. | Free source; local or hosted infrastructure required |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Select a chapter about objectives, alerts, incidents, or releases rather than reading everything in order. | Free online book |

[k6](../04-tools-and-technologies/k6.md) · [Locust](../04-tools-and-technologies/locust.md) · [Chaos Mesh](../04-tools-and-technologies/chaos-mesh.md) · [Toxiproxy](../04-tools-and-technologies/toxiproxy.md)

## Make the exercise useful

Apply a bounded load or reversible fault to an owned test application and compare the relevant service observations. Keep the workload model, affected scope, baseline, and verified recovery.

**Environment and cleanup:** Stop load generators and fault injection, restore the learning configuration, and delete temporary telemetry or application resources.

[Browse this collection](README.md) · [Directory homepage](../README.md)

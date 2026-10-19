# Cloud Reliability

Start with a user-visible objective and examine the provider dependencies behind it.

## Compare guidance with the workload

| Open | What you can find | Access |
| --- | --- | --- |
| [AWS Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) | Explore workload reliability questions and service dependencies. | Free reference; implementation can incur charges |
| [Azure Well-Architected reliability](https://learn.microsoft.com/en-us/azure/well-architected/reliability/) | Read the reliability guidance against a workload’s actual requirements. | Public guidance; implementation costs vary |
| [Google Cloud reliability framework](https://cloud.google.com/architecture/framework/reliability) | Find provider guidance around resilient workload design. | Public guidance; implementation costs vary |
| [Implementing SLOs](https://sre.google/workbook/implementing-slos/) | Connect a reliability objective to a user-visible behavior and a measurement. | Free online chapter |
| [Amazon Builders’ Library](https://aws.amazon.com/builders-library/) | Explore engineering articles about operating distributed services. | Free engineering library |
| [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) | Select a chapter about objectives, alerts, incidents, or releases rather than reading everything in order. | Free online book |

## Tools you can follow

[Prometheus](../04-tools-and-technologies/prometheus.md) · [k6](../04-tools-and-technologies/k6.md) · [Terraform](../04-tools-and-technologies/terraform.md)

## Choose a bounded exercise

Map one user action to its dependencies and explain how you would observe a failure and verify recovery in a learning environment. Check the selected guide’s permissions, region, account, and resource requirements before starting. Follow its teardown, revoke temporary access, and inspect retained disks, snapshots, addresses, logs, or other billable resources afterward.

[Browse this collection](README.md) · [Directory homepage](../README.md)

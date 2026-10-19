# Cloud Security References and Practice

Use provider-specific controls alongside a clear explanation of the boundary you want to protect.

## Choose a workload protection question

| Open | What you can find | Access |
| --- | --- | --- |
| [AWS Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html) | Select the workload-protection question behind a provider configuration. | Free reference; implementation can incur charges |
| [Microsoft cloud security benchmark](https://learn.microsoft.com/en-us/security/benchmark/azure/overview) | Check the benchmark version and control guidance before applying it. | Public guidance; inspect preview status |
| [Google Cloud security foundations](https://cloud.google.com/security/best-practices) | Choose a provider-specific guide for identity, data, or workload protection. | Public guide catalog |
| [IAM policy simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) | Compare simulated decisions with the guide’s stated limitations. | Free documentation; permissions and account required |
| [Security Engineering](https://www.cl.cam.ac.uk/archive/rja14/book.html) | Ross Anderson; choose a security-design chapter to understand the assumptions around a control. | Author-hosted material; edition access varies |

## Tools you can follow

[Vault](../04-tools-and-technologies/vault.md) · [OpenBao](../04-tools-and-technologies/openbao.md) · [Checkov](../04-tools-and-technologies/checkov.md) · [Trivy](../04-tools-and-technologies/trivy.md)

## Choose a bounded exercise

Demonstrate an intended and denied operation with synthetic data, preserving the policy and redacted result. Check the selected guide’s permissions, region, account, and resource requirements before starting. Follow its teardown, revoke temporary access, and inspect retained disks, snapshots, addresses, logs, or other billable resources afterward.

[Browse this collection](README.md) · [Directory homepage](../README.md)

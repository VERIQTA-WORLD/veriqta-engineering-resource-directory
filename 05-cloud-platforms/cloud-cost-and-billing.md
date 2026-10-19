# Cloud Cost and Billing

Discover resources that make an estimate’s assumptions and the workload’s ownership visible.

## Make the estimate explainable

| Open | What you can find | Access |
| --- | --- | --- |
| [FinOps Framework](https://www.finops.org/framework/) | Connect cloud cost work with allocation, ownership, and engineering decisions. | Public framework |
| [AWS Pricing Calculator](https://calculator.aws/) | Model the services and usage assumptions behind an AWS estimate. | Public estimator; estimates are not a bill |
| [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/) | Estimate selected Azure resources using explicit usage assumptions. | Public estimator; inspect currency and regional settings |
| [Google Cloud Pricing Calculator](https://cloud.google.com/products/calculator) | Compare a Google Cloud workload estimate with its assumed resources and use. | Public estimator; estimates and actual charges can differ |

## Tools you can follow

[AWS CLI](../04-tools-and-technologies/aws-cli.md) · [Azure CLI](../04-tools-and-technologies/azure-cli.md) · [gcloud CLI](../04-tools-and-technologies/gcloud.md) · [Terraform](../04-tools-and-technologies/terraform.md)

## Choose a bounded exercise

Estimate a small dedicated workload, inventory what was created, and inspect retained billable resources after teardown. Check the selected guide’s permissions, region, account, and resource requirements before starting. Follow its teardown, revoke temporary access, and inspect retained disks, snapshots, addresses, logs, or other billable resources afterward.

[Browse this collection](README.md) · [Directory homepage](../README.md)

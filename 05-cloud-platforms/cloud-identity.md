# Cloud Identity and Access

Choose the provider identity model before comparing permissions examples across clouds.

## Find the provider reference

| Open | What you can find | Access |
| --- | --- | --- |
| [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) | Study the policy context behind an allowed or denied action. | Free reference; AWS account for practice |
| [IAM policy simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) | Compare simulated decisions with the guide’s stated limitations. | Free documentation; permissions and account required |
| [Microsoft Entra documentation](https://learn.microsoft.com/en-us/entra/) | Choose the identity product and access scenario before following a guide. | Public reference; tenant and feature requirements vary |
| [Google Cloud IAM overview](https://cloud.google.com/iam/docs/overview) | Read the provider’s identity and authorization model. | Public reference; project permissions for practice |
| [Security Engineering](https://www.cl.cam.ac.uk/archive/rja14/book.html) | Ross Anderson; choose a security-design chapter to understand the assumptions around a control. | Author-hosted material; edition access varies |

## Tools you can follow

[AWS CLI](../04-tools-and-technologies/aws-cli.md) · [Azure CLI](../04-tools-and-technologies/azure-cli.md) · [gcloud CLI](../04-tools-and-technologies/gcloud.md) · [Vault](../04-tools-and-technologies/vault.md)

## Choose a bounded exercise

For one synthetic access test, record the principal, action, resource, and context for an allowed and a denied result. Check the selected guide’s permissions, region, account, and resource requirements before starting. Follow its teardown, revoke temporary access, and inspect retained disks, snapshots, addresses, logs, or other billable resources afterward.

[Browse this collection](README.md) · [Directory homepage](../README.md)

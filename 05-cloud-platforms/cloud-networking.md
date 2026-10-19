# Cloud Networking

Follow a request through names, routes, access rules, and the destination workload.

## Choose a network model

| Open | What you can find | Access |
| --- | --- | --- |
| [Amazon VPC user guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html) | Follow subnets and routing into a provider network model. | Free reference; provisioned resources can cost money |
| [Azure Virtual Network](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview) | Connect subnets and connectivity to the provider network model. | Public reference; infrastructure charges may apply |
| [Google Cloud VPC](https://cloud.google.com/vpc/docs/overview) | Study the provider’s network concepts before building a test topology. | Public reference; infrastructure charges may apply |
| [Networking Fundamentals](https://www.practicalnetworking.net/index/networking-fundamentals-how-data-moves-through-the-internet/) | Follow the free introductory module on how data moves through networks. | Free module; further training separate |
| [Computer Networks: A Systems Approach](https://book.systemsapproach.org/) | Larry Peterson and Bruce Davie; connect protocols to the systems they support. | Free online textbook |

## Tools you can follow

[Wireshark](../04-tools-and-technologies/wireshark.md) · [Terraform](../04-tools-and-technologies/terraform.md) · [iproute2](../04-tools-and-technologies/iproute2.md)

## Choose a bounded exercise

Draw a dedicated learning network and verify the expected path and one intentionally unavailable destination. Check the selected guide’s permissions, region, account, and resource requirements before starting. Follow its teardown, revoke temporary access, and inspect retained disks, snapshots, addresses, logs, or other billable resources afterward.

[Browse this collection](README.md) · [Directory homepage](../README.md)

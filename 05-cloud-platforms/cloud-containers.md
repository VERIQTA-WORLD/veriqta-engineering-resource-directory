# Cloud Containers and Managed Kubernetes

Choose the operating model before comparing deployment tutorials.

## Compare the service boundaries

| Open | What you can find | Access |
| --- | --- | --- |
| [Amazon ECS developer guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) | Explore task, service, and cluster concepts for an AWS container workload. | Free reference; workload charges may apply |
| [Amazon EKS user guide](https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html) | Distinguish the managed Kubernetes service from workload and account responsibilities. | Free reference; cluster and workload charges may apply |
| [Azure Kubernetes Service](https://learn.microsoft.com/en-us/azure/aks/) | Find the managed-cluster task matching your deployment or operation question. | Free reference; infrastructure charges may apply |
| [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine/docs/concepts/kubernetes-engine-overview) | Choose the managed Kubernetes operating model relevant to your workload. | Free reference; infrastructure charges may apply |
| [Kubernetes 101 with Jeff Geerling](https://kube101.jeffgeerling.com/) | Follow an application through Kubernetes concepts with a creator’s recorded teaching series. | Free video series; check current APIs |
| [Kubernetes in Action, Second Edition](https://www.manning.com/books/kubernetes-in-action-second-edition) | Marko Lukša and Kevin Conner; use the contents to select the workload or cluster subject you need. | Paid book; publisher samples |

## Tools you can follow

[Docker](../04-tools-and-technologies/docker.md) · [Kubernetes](../04-tools-and-technologies/kubernetes.md) · [Helm](../04-tools-and-technologies/helm.md) · [Terraform](../04-tools-and-technologies/terraform.md)

## Choose a bounded exercise

Run a small learning application in one chosen service and identify which operating tasks the provider handles and which remain yours. Check the selected guide’s permissions, region, account, and resource requirements before starting. Follow its teardown, revoke temporary access, and inspect retained disks, snapshots, addresses, logs, or other billable resources afterward.

[Browse this collection](README.md) · [Directory homepage](../README.md)

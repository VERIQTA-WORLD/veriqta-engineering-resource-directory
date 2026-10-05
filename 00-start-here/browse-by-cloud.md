# Browse by cloud

Browse by cloud when you need to understand a specific provider, platform, or operating context. Use this route alongside technical domains: the environment-specific view explains implementation choices, while domains explain the concepts behind them.

This guide is for learners and engineers choosing where to begin. It is a navigation guide, not a current comparison of service availability, pricing, or vendor capabilities. Many destination files remain under development.

## Understand the classification

The cloud section contains more than public-cloud vendors. It also includes platforms, managed-service models, and environments such as hybrid cloud. They belong together because readers may approach them through similar operational questions, but they should not be treated as identical categories.

| Kind of context | How to use its material |
| --- | --- |
| Named provider | Explore the provider's services, identity model, architecture, operations, and official documentation |
| Infrastructure or application platform | Understand platform components, deployment choices, responsibility boundaries, and integrations |
| Operating model | Study how environments are combined or managed, including ownership and cross-environment dependencies |
| Comparison context | Compare options against explicit requirements rather than a universal ranking |

For example, a platform may run on infrastructure supplied by a provider. A hybrid environment may combine several kinds of infrastructure. These distinctions affect who owns networking, upgrades, recovery, and support.

## Find a named provider folder

The following are repository locations, not endorsements or a claim that their products are equivalent:

| Folder | Folder | Folder |
| --- | --- | --- |
| [AWS](../04-cloud-providers/aws/) | [Azure](../04-cloud-providers/azure/) | [Google Cloud](../04-cloud-providers/google-cloud/) |
| [Alibaba Cloud](../04-cloud-providers/alibaba-cloud/) | [Oracle Cloud](../04-cloud-providers/oracle-cloud/) | [IBM Cloud](../04-cloud-providers/ibm-cloud/) |
| [DigitalOcean](../04-cloud-providers/digitalocean/) | [Akamai Cloud](../04-cloud-providers/akamai-cloud/) | [Cloudflare](../04-cloud-providers/cloudflare/) |
| [Hetzner](../04-cloud-providers/hetzner/) | [OVHcloud](../04-cloud-providers/ovhcloud/) | [Scaleway](../04-cloud-providers/scaleway/) |
| [Vultr](../04-cloud-providers/vultr/) | [Equinix](../04-cloud-providers/equinix/) | |

Folder labels follow the repository structure. Check the relevant official documentation when a decision depends on a current product name, service, location, commercial term, or support arrangement.

## Find a platform or operating context

| Location | Questions to investigate |
| --- | --- |
| [OpenStack](../04-cloud-providers/openstack/) | What are the platform components and infrastructure operating responsibilities? |
| [OpenShift](../04-cloud-providers/openshift/) | What does the platform supply, and what remains with the application or infrastructure team? |
| [Nutanix](../04-cloud-providers/nutanix/) | Which deployment and operating context is relevant to the requirement? |
| [VMware Cloud](../04-cloud-providers/vmware-cloud/) | What platform and service arrangement does the environment use? |
| [Bare metal cloud](../04-cloud-providers/bare-metal-cloud/) | Which physical-host responsibilities and constraints apply? |
| [Hybrid cloud](../04-cloud-providers/hybrid-cloud/) | How are different environments connected and operated? |
| [Multi-cloud](../04-cloud-providers/multi-cloud/) | Why are multiple providers involved, and how are identity, networking, data, and operations coordinated? |
| [Edge cloud](../04-cloud-providers/edge-cloud/) | How do placement and distributed operation affect the workload? |
| [PaaS](../04-cloud-providers/paas/) | Which application platform responsibilities are managed and which remain with the team? |
| [Cloud comparison](../04-cloud-providers/cloud-comparison/) | Which requirements determine a fair comparison? |

## Choose an operational topic

Within an applicable cloud folder, the files separate major concerns. Use the README first, then choose the topic closest to the question:

- Architecture explains the system's boundaries and design choices.
- Identity/security and governance explain access, controls, and ownership.
- Networking explains communication and connectivity.
- Compute, containers/Kubernetes, and serverless describe execution choices.
- Storage and databases describe data responsibilities.
- CLI/SDK, automation, and infrastructure as code describe repeatable management.
- Delivery material connects changes and application releases to the environment.
- Observability and status/troubleshooting address operational evidence.
- Backup/disaster recovery addresses recovery requirements and validation.
- Cost/FinOps and migration/hybrid address financial and transition decisions.
- Documentation and learning/certification provide references and learning routes.

CLI means command-line interface; SDK means software development kit. Their instructions must state authentication and execution context before practical use.

A topic may not apply in the same way to every folder. Read its scope instead of assuming that matching filenames imply matching capabilities.

## Follow a practical browsing journey

**Illustrative example:** your team already uses one provider and wants to run a new service.

Begin with the workload requirements: traffic, data, access, recovery expectations, operational skills, and budget. Use the provider's architecture material to identify the relevant components. Check identity and networking before assuming connectivity. Explore the execution and data topics, then observability, recovery, and cost.

Consult the exact official sources for the intended services and versions. A concept demonstrated on one provider may require a different configuration or responsibility boundary on another.

## Compare environments fairly

Start with constraints, not a popularity ranking. Consider data location, dependencies, team skills, access, required capabilities, support, recovery, capacity, and the cost model. Include operational effort and migration implications alongside service charges.

Record what has been measured, what comes from documentation, and what is an assumption. Avoid claiming one provider is always cheaper or safer. A controlled proof of concept should test the requirements that matter to the workload.

## Before hands-on work

Confirm account/project, region, permissions, quotas, versions, chargeable resources, and cleanup. Use a disposable environment when following a learning exercise. Do not assume account access is unlimited or a free tier covers every step.

Continue with the [cloud section](../04-cloud-providers/), use [domains](browse-by-domain.md) to fill conceptual gaps, or read [Find a tool](find-a-tool.md) for a selection framework.

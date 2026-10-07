# DevOps architect: labs and portfolio projects

Use these practical resources to test a design assumption and produce evidence you can explain. They range from local introductory exercises to advanced cloud reference implementations. Choose a resource for its engineering question, not for the number of products you can put in a diagram.

The descriptions identify prerequisites, portfolio evidence, and cleanup concerns. The sources were inspected; these exercises were not executed for this directory. Check the current instructions before running them. No cloud budget or production permission is assumed.

## Find a practical resource

- [Local Kubernetes with kind](#local-kubernetes-with-kind)
- [Local Kubernetes with minikube](#local-kubernetes-with-minikube)
- [Build and share a containerized application](#build-and-share-a-containerized-application)
- [Infrastructure lifecycle with local Docker](#infrastructure-lifecycle-with-local-docker)
- [Desired-state application delivery with Argo CD](#desired-state-application-delivery-with-argo-cd)
- [Bootstrap a Flux-managed environment](#bootstrap-a-flux-managed-environment)
- [Cloud Kubernetes with the EKS Workshop](#cloud-kubernetes-with-the-eks-workshop)
- [Azure AKS baseline reference implementation](#azure-aks-baseline-reference-implementation)
- [Google Cloud enterprise foundation example](#google-cloud-enterprise-foundation-example)
- [Focused cloud-control experiments](#focused-cloud-control-experiments)
- [Distributed tracing with the OpenTelemetry Demo](#distributed-tracing-with-the-opentelemetry-demo)
- [Metrics collection with Prometheus](#metrics-collection-with-prometheus)
- [Performance checks with k6](#performance-checks-with-k6)
- [Backstage portal foundations](#backstage-portal-foundations)
- [Reusable project scaffolding](#reusable-project-scaffolding)
- [Admission-policy examples with Kyverno](#admission-policy-examples-with-kyverno)
- [Rego policy experiments](#rego-policy-experiments)
- [Artifact signing and verification](#artifact-signing-and-verification)

## Local Kubernetes with kind

**Source:** [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/).

**You need:** Foundation to intermediate; container engine, command-line familiarity, and enough local memory.

**Use it to:** Inspect a local cluster and a small application so you can reason about scheduling, services, and application changes without starting with cloud accounts.

**Evidence to keep:** Keep the cluster configuration, workload manifests, observation notes, and the result of an application update. Local success does not establish a highly available production control plane.

**Cleanup and limits:** Use the guide's cluster-deletion instructions. Check for locally retained images and containers; do not delete a cluster you use for other work.

## Local Kubernetes with minikube

**Source:** [minikube start guide](https://minikube.sigs.k8s.io/docs/start/).

**You need:** Foundation to intermediate; use a supported local driver and the guide's system requirements.

**Use it to:** Compare a local cluster workflow with kind, especially host integration, drivers, and optional addons. Choose one for the first experiment rather than installing both without a reason.

**Evidence to keep:** Document the driver, exposed endpoints, addon choices, and the difference between a stopped and removed environment.

**Cleanup and limits:** Use the source's stop/delete guidance for the intended profile. Inspect retained volumes or driver resources before assuming cleanup is complete.

## Build and share a containerized application

**Source:** [Docker workshop](https://docs.docker.com/get-started/workshop/).

**You need:** Foundation; a suitable Docker environment and basic shell familiarity. Registry publication requires an appropriate account.

**Use it to:** Follow the official application exercise and inspect image, runtime, networking, and storage choices. Keep the application isolated from sensitive local files.

**Evidence to keep:** Retain the Dockerfile, image identifier, service explanation, and observations about persistent data. Publishing an image makes it available according to registry permissions.

**Cleanup and limits:** Review the cleanup commands included by the workshop. Remove only the exercise's containers, networks, and volumes; review pushed registry artifacts separately.

## Infrastructure lifecycle with local Docker

**Source:** [Terraform Docker tutorial collection](https://developer.hashicorp.com/terraform/tutorials/docker-get-started).

**You need:** Foundation; Terraform CLI and a working Docker environment.

**Use it to:** Use the tutorial collection to inspect configuration, plan, apply, state, change, and destroy with local resources. This is a guided workflow, not a cloud landing-zone design.

**Evidence to keep:** Capture a sanitized plan and explain which resource changes after a configuration edit. Keep state free of unrelated resources.

**Cleanup and limits:** Follow the collection's destroy tutorial, then check its managed containers and state. Never apply destroy to a shared or unrelated state file.

## Desired-state application delivery with Argo CD

**Source:** [Argo CD example applications](https://github.com/argoproj/argocd-example-apps).

**You need:** Intermediate; disposable Kubernetes cluster, Argo CD installation, and familiarity with repository-backed manifests.

**Use it to:** Choose one example application and study the relationship between repository state, application configuration, live resources, and synchronization. The repository supplies examples, not a complete production deployment.

**Evidence to keep:** Keep an application manifest, a drift observation, and an explanation of the chosen synchronization policy and permissions.

**Cleanup and limits:** No single teardown covers every example. Remove the application and exercise resources according to ownership, revoke disposable credentials, and delete the dedicated cluster if used.

## Bootstrap a Flux-managed environment

**Source:** [Flux getting started](https://fluxcd.io/flux/get-started/).

**You need:** Intermediate; disposable cluster, Git access, required CLI, and permissions for the selected bootstrap provider.

**Use it to:** Follow the official bootstrap route and track which repository objects and cluster controllers it creates. Explain how subsequent changes reach the cluster.

**Evidence to keep:** Retain sanitized bootstrap configuration, reconciliation status, and a documented update. Explain the effect of pausing or removing reconciliation.

**Cleanup and limits:** Read the [Flux uninstall reference](https://fluxcd.io/flux/cmd/flux_uninstall/) and inspect repository resources and credentials separately. Cluster deletion alone does not revoke a repository token.

## Cloud Kubernetes with the EKS Workshop

**Source:** [Amazon EKS Workshop](https://www.eksworkshop.com/).

**You need:** Intermediate to advanced; AWS account, required permissions, budget, CLI setup, and the chosen module prerequisites.

**Use it to:** Choose a module that tests one design question, such as workload access, networking, observability, or scaling. The workshop is a collection; not every module is necessary for your portfolio.

**Evidence to keep:** Record the module, architecture assumption, actual result, and AWS resources created. Managed clusters and auxiliary services can incur charges.

**Cleanup and limits:** Follow the workshop's cleanup section and the selected module's additional teardown. Check retained volumes, load balancers, roles, and other resources in the account.

## Azure AKS baseline reference implementation

**Source:** [AKS baseline implementation](https://github.com/mspnp/aks-baseline).

**You need:** Advanced; Azure subscription, required deployment permissions, infrastructure-tool familiarity, and budget.

**Use it to:** Inspect the repository's deployment model and prerequisites before running it. Use it to evaluate the documented AKS baseline rather than to claim you designed a production platform from scratch.

**Evidence to keep:** Compare the reference architecture with the deployed resources; explain network, identity, operational, and cost decisions you would change for another workload.

**Cleanup and limits:** Use the implementation's removal instructions and verify dependent or retained resources. Deployment creates billable Azure infrastructure; confirm deletion in the subscription.

## Google Cloud enterprise foundation example

**Source:** [Google Cloud example foundation](https://github.com/terraform-google-modules/terraform-example-foundation).

**You need:** Advanced; appropriate organization and project authority, Terraform knowledge, billing setup, and familiarity with the blueprint.

**Use it to:** Review a selected stage and its account, identity, network, and policy assumptions. This multi-stage foundation is not a safe first Terraform exercise.

**Evidence to keep:** Produce a stage/dependency map and an ownership review before deployment. If you deploy, retain sanitized evidence of controls and the resources actually created.

**Cleanup and limits:** Teardown depends on the stages and their dependencies; follow repository instructions and plan deletion explicitly. Do not assume one destroy command safely removes an organization foundation.

## Focused cloud-control experiments

**Source:** [AWS Well-Architected Labs](https://www.wellarchitectedlabs.com/).

**You need:** Intermediate to advanced; selected AWS lab prerequisites, account authority, and budget.

**Use it to:** Select a named lab that supports your design question. The landing page is a discovery collection; inspect the actual lab before allocating permissions or infrastructure.

**Evidence to keep:** Record the selected lab, the control tested, its result, and the charges or resources it could leave behind.

**Cleanup and limits:** Use the selected lab's cleanup instructions. This directory does not certify every lab in the collection or guarantee that teardown is complete.

## Distributed tracing with the OpenTelemetry Demo

**Source:** [OpenTelemetry Demo](https://opentelemetry.io/docs/demo/).

**You need:** Intermediate; supported local or Kubernetes deployment environment and enough memory for the selected setup.

**Use it to:** Trace requests across the demonstration services and observe how telemetry reaches the configured backends. Use synthetic traffic rather than real customer payloads.

**Evidence to keep:** Keep a request trace, a component map, and an explanation of where instrumentation, collection, and query access are configured.

**Cleanup and limits:** Follow the chosen deployment method's teardown; inspect volumes and external integrations. The full demo can be resource-intensive.

## Metrics collection with Prometheus

**Source:** [Prometheus getting started](https://prometheus.io/docs/prometheus/latest/getting_started/).

**You need:** Foundation to intermediate; local process or container execution and familiarity with metrics endpoints.

**Use it to:** Follow the official getting-started route and inspect targets, metric labels, querying, and basic rule configuration.

**Evidence to keep:** Keep a successful target observation, a query explanation, and an example of a missing or invalid target. Do not expose an unauthenticated demo to the internet.

**Cleanup and limits:** Stop and remove only the exercise process/container and its local data as appropriate. The introduction is not a full production storage or retention design.

## Performance checks with k6

**Source:** [Running k6](https://grafana.com/docs/k6/latest/get-started/running-k6/).

**You need:** Intermediate; k6 installation, basic scripting knowledge, and a target you own or are authorized to test.

**Use it to:** Write a small test against a local sample application and distinguish request failures, checks, and thresholds. Avoid public services and uncontrolled load.

**Evidence to keep:** Retain the test, workload assumptions, result summary, and an explanation of the threshold decision. More virtual users do not automatically model real usage.

**Cleanup and limits:** Stop local test services and remove exercise artifacts as desired. If a hosted testing service is used, inspect its account and retention settings separately.

## Backstage portal foundations

**Source:** [Backstage getting started](https://backstage.io/docs/getting-started/).

**You need:** Intermediate; the currently documented Node.js/toolchain prerequisites and application-development familiarity.

**Use it to:** Create a local portal and inspect its catalog and configuration. Keep initial experiments local rather than exposing an unfinished authentication setup.

**Evidence to keep:** Explain the boundary between portal UI, catalog metadata, backend integrations, and the systems those integrations can change.

**Cleanup and limits:** Stop the development services and remove only the exercise directory and dedicated resources. Revoke any test integration credentials you configured.

## Reusable project scaffolding

**Source:** [Backstage Software Templates](https://backstage.io/docs/features/software-templates/).

**You need:** Intermediate; a running Backstage environment and understanding of its scaffolder actions.

**Use it to:** Design a template for a small sample service, then inspect how inputs become files and repository actions. Review action permissions and untrusted input handling.

**Evidence to keep:** Keep the template, generated project, permissions explanation, and a record of validation failures. Scaffolding does not certify the generated service's operating readiness.

**Cleanup and limits:** Remove generated test repositories and revoke disposable tokens where used. The feature documentation is an implementation reference; teardown depends on the integrations you choose.

## Admission-policy examples with Kyverno

**Source:** [Kyverno policy library](https://kyverno.io/policies/).

**You need:** Intermediate; disposable Kubernetes environment, compatible Kyverno release, and admission-policy knowledge.

**Use it to:** Choose a policy relevant to a real requirement and test both an accepted and rejected synthetic workload. Inspect enforcement mode and exceptions before applying it.

**Evidence to keep:** Keep the policy, test inputs, expected and actual results, and an exception/ownership explanation. A library example is not an organization-approved control.

**Cleanup and limits:** Remove the test policy and workloads using their known names. The library has no universal cleanup path; cluster removal is an option only for a dedicated lab cluster.

## Rego policy experiments

**Source:** [OPA Rego learning examples](https://www.openpolicyagent.org/docs/policy-language).

**You need:** Foundation to intermediate; browser and basic structured-data knowledge. The guide links the official playground.

**Use it to:** Use the source examples to evaluate a small authorization rule against synthetic allow and deny inputs. Inspect policy semantics before embedding a policy engine.

**Evidence to keep:** Retain the policy and test cases, including an unexpected or missing input. Explain what the policy evaluates and what enforcement component would consume the result.

**Cleanup and limits:** No cloud infrastructure is needed for the browser exercise. The guide was reviewed; the interactive application was not executed. Do not submit secrets or private records; consider what is saved or shared before publishing a playground link.

## Artifact signing and verification

**Source:** [Cosign signing quickstart](https://docs.sigstore.dev/quickstart/quickstart-cosign/).

**You need:** Intermediate; Cosign installation and the quickstart's identity, registry, and artifact prerequisites.

**Use it to:** Follow the source's signing and verification workflow for an exercise artifact and examine the identity and trust conditions.

**Evidence to keep:** Retain the artifact digest, verification policy, and a failed verification case without exposing credentials. Signature presence alone does not establish artifact safety.

**Cleanup and limits:** Remove disposable registry artifacts and credentials where appropriate. Public transparency-log records may remain after local or registry cleanup; use synthetic names and content.

## Portfolio combinations you can adapt

These are original project briefs assembled around the linked references above. They are not claims that a complete ready-made tutorial exists for each combination. Use the source instructions for implementation, and keep the environment disposable.

| Project brief | Starting resources above | What makes the result useful |
| --- | --- | --- |
| A local application delivery path | Docker, Terraform Docker, kind or minikube, then Argo CD or Flux | Trace source/configuration to a deployed application; show drift, controlled update, and teardown |
| A service with diagnostic evidence | OpenTelemetry Demo, Prometheus, and a small authorized k6 test | Show a request path, useful signals, a bounded failure, and the evidence you used to distinguish hypotheses |
| A guarded deployment interface | Kyverno examples, Rego experiments, and the signing quickstart | Show accepted and rejected cases, identity assumptions, exceptions, and the control's limits |
| A platform workflow with clear ownership | Backstage installation and Software Templates | Demonstrate a user task, generated artifacts, action authority, and the operating boundary behind the portal |
| A cloud baseline design review | One provider implementation and its architecture reference | Explain required authority, workload assumptions, operating responsibilities, cost, and a realistic teardown plan |

## Present the work honestly

Include your goal, environment, architecture decision, source attribution, changes you made, observations, failures, and cleanup evidence. State which components came from a reference. Use sanitized logs and diagrams; exclude secrets, customer data, and unauthorized screenshots. A runnable demo is useful evidence of a workflow, not proof of production readiness.

You can also produce a design-only portfolio item when deployment would be too costly. Label it clearly and include the assumptions, validation plan, and unresolved questions instead of invented runtime results.

[Architecture references](devops-architect-architecture-resources.md) · [Production-practice resources](devops-architect-production-practices.md) · [Discuss and assess your evidence](devops-architect-interview-and-assessment-resources.md)

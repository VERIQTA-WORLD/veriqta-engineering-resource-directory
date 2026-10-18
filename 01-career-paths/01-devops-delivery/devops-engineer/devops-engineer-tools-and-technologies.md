# DevOps Engineer: Tools and Technology Resources

Choose a working set of delivery tools that you can explain and maintain. Compare their responsibilities and integration behavior before expanding the stack.

This page focuses on implementing and operating the path from source changes to usable services. **Question to keep in view:** Can you trace the deployed artifact to its source and establish whether users can use it?

## On this page

- [Build one coherent delivery path](#build-one-coherent-delivery-path)
- [Separate packaging and orchestration](#separate-packaging-and-orchestration)
- [Use observability to answer questions](#use-observability-to-answer-questions)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Build one coherent delivery path

Choose a repository workflow, artifact format, target environment, and acceptance method. Connect them using explicit identities and inputs. Adding several alternatives at once makes it harder to tell whether a failure belongs to application behavior or the delivery mechanism.

## Separate packaging and orchestration

A container image packages an application environment; orchestration adds scheduling and workload coordination. Adopt orchestration when the workload and operating needs justify it. A local container is often enough to learn artifact and configuration behavior first.

## Use observability to answer questions

Select signals that explain user outcomes and dependencies. Decide where telemetry is collected, retained, and queried. A dashboard with many charts is less useful than a small set of observations tied to release acceptance and investigation.

## Compare tools against the same task

For each candidate, record the responsibility it owns, its inputs and outputs, required authority, stored state, operator burden, and failure behavior. Reject options that cannot satisfy a mandatory requirement. Compare remaining options using the same workload and team assumptions; a longer feature list is not a decision criterion by itself.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [GitHub Actions documentation](https://docs.github.com/en/actions)

**Use it to answer:** What triggers the workflow, where does it execute, and which result does it actually establish?

- **Start with:** The relevant concepts, how-to guide, and reference for your task.
- **Prerequisites:** Git and repository workflow familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-actions) for publisher context, access conditions, and the key limitation.

### [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/)

**Use it to answer:** How do the application image, runtime configuration, network exposure, and persistent data relate?

- **Start with:** Before you start, then the application workflow.
- **Prerequisites:** Docker software, Git, and the account requirements in the guide.
- **Access and limits:** See the [maintained source annotation](../README.md#source-docker) for publisher context, access conditions, and the key limitation.

### [Kubernetes overview](https://kubernetes.io/docs/concepts/overview/)

**Use it to answer:** Which orchestration responsibility is necessary for this workload, and what remains the application owner's concern?

- **Start with:** What Kubernetes does and the linked concepts.
- **Prerequisites:** Containers, basic networking, and application configuration.
- **Access and limits:** See the [maintained source annotation](../README.md#source-kube) for publisher context, access conditions, and the key limitation.

### [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/)

**Use it to answer:** Which desired state is authoritative, what can the reconciler change, and how is disagreement exposed?

- **Start with:** Core concepts, then the relevant user guide.
- **Prerequisites:** Kubernetes resources, Git, and application deployment knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-argo) for publisher context, access conditions, and the key limitation.

### [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/)

**Use it to answer:** Which signals can connect the user symptom to the dependency or operation you need to inspect?

- **Start with:** Signals relevant to your diagnostic question.
- **Prerequisites:** Basic distributed application and observability concepts.
- **Access and limits:** See the [maintained source annotation](../README.md#source-otel) for publisher context, access conditions, and the key limitation.

## Apply the reading

Compare a simple host deployment and a Kubernetes deployment for the same small service. Record what each adds to operating responsibility, acceptance evidence, and recovery.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

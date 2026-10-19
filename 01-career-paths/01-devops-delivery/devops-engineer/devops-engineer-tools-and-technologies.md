# DevOps Engineer: Tools and Technology Resources

Start with one delivery path you can inspect from source to a functional request. Expand the stack when a specific requirement justifies it.

## Build one coherent delivery path

Choose a repository workflow, artifact format, target environment, and acceptance method. Connect them using explicit identities and inputs. Adding several alternatives at once makes it harder to tell whether a failure belongs to application behavior or the delivery mechanism.

## Separate packaging and orchestration

A container image packages an application environment; orchestration adds scheduling and workload coordination. Adopt orchestration when the workload and operating needs justify it. A local container is often enough to learn artifact and configuration behavior first.

## Use observability to answer questions

Select signals that explain user outcomes and dependencies. Decide where telemetry is collected, retained, and queried. A dashboard with many charts is less useful than a small set of observations tied to release acceptance and investigation.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Docker | Use packaging to make the application and its runtime inputs easier to reproduce. | Check configuration, persistence, listener, and registry behavior separately. |
| GitHub Actions | Use repository events to run understandable checks and delivery steps. | Confirm event trust, permissions, artifact identity, and the actual deployment destination. |
| OpenTelemetry | Use signals to investigate requests and their dependencies. | Decide where signals are collected and queried; instrumentation alone does not provide a complete operating service. |

## Implementation and diagnostic references

- [GitHub Actions documentation](https://docs.github.com/en/actions): The relevant concepts, how-to guide, and reference for your task. [Access and technical limits](../README.md#source-actions).
- [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/): Before you start, then the application workflow. [Access and technical limits](../README.md#source-docker).
- [Kubernetes overview](https://kubernetes.io/docs/concepts/overview/): What Kubernetes does and the linked concepts. [Access and technical limits](../README.md#source-kube).
- [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/): Core concepts, then the relevant user guide. [Access and technical limits](../README.md#source-argo).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).

[Back to DevOps Engineer resources](README.md) · [Browse this career collection](../README.md)

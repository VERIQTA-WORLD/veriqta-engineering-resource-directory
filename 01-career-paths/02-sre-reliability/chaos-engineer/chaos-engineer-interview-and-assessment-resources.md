# Chaos Engineer: Interview and Assessment Resources

The useful answer identifies what the experiment would establish and what it could damage before discussing how to run it.

## Multiple replicas are called resilient

Ask which failure the replicas are intended to tolerate and whether shared dependencies invalidate the claim. Form a hypothesis with a representative request, acceptance boundary, and observable rejection condition.

## The stop alarm uses the failing path

Explain how you would detect impact when telemetry or control depends on the disrupted service. Compare an independent observer, a narrower experiment, and postponing until safe control is available.

## The experiment ends but latency stays high

Investigate backlog, reconnection, rescheduling, cache state, and external effects. Explain why injection completion is not recovery and which evidence you need before declaring the service restored.

## What to look for in your answer

State the hypothesis and rejection condition first. Then explain target scope, independent control, residual effects, and recovery evidence. Increasing fault severity without resolving those questions weakens the experiment.

## References for checking the reasoning

- [Chaos Mesh documentation](https://chaos-mesh.org/docs/) · [Access and technical limits](../README.md#source-chaos)
- [AWS Fault Injection Service overview](https://docs.aws.amazon.com/fis/latest/userguide/what-is.html) · [Access and technical limits](../README.md#source-fis)
- [Kubernetes: Disruptions](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/) · [Access and technical limits](../README.md#source-disruption)

[Back to Chaos Engineer resources](README.md) · [Browse this career collection](../README.md)

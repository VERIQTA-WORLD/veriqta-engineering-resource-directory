# Network Reliability Engineer: Tools and Technology Resources

Choose the observation point first. A successful administrator check may take a different path from the failing application.

## Choose a vantage point first

Select observations from the client, host, proxy, workload, or network boundary according to the hypothesis. Use scoped diagnostic access. A check from an administrator workstation may bypass the exact path failing for an application.

## Combine layer-specific and service evidence

Use resolver checks, connection observations, platform telemetry, and functional requests together. Telemetry can connect a failing request to an upstream dependency. Packet visibility alone cannot establish that the application returned the correct result.

## What each choice buys you

| Choice | Why you might use it | What to check |
| --- | --- | --- |
| Resolver observations | Use them to establish the name, record type, response, and cache context. | Resolution success leaves transport, policy, encryption, and application behavior open. |
| Host-network evidence | Use subsystem-specific observations when the failing boundary points to the host. | Match kernel and platform context; an observation from another path can mislead. |
| Request correlation | Use service telemetry to connect a failed operation with its dependency. | Sampling, collection gaps, and clock context affect what you can infer. |

## Implementation and diagnostic references

- [Linux kernel networking documentation](https://docs.kernel.org/networking/index.html): The subsystem relevant to your observed host-network behavior. [Access and technical limits](../README.md#source-kernel-net).
- [Kubernetes: Debugging DNS Resolution](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/): Prerequisites and the checks matching the failing boundary. [Access and technical limits](../README.md#source-kube-dns).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).

## Reading behind the tool decision

- [RFC 1035: Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035): Message structure, resource records, and caching concepts. [Access and technical limits](../README.md#source-dns).
- [RFC 8446: TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446): Handshake concepts and the part relevant to your connection problem. [Access and technical limits](../README.md#source-tls).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Network Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Network Reliability Engineer: Role and Responsibility Resources

Begin with the failing source, destination, time, and request. “The network is down” does not yet identify a boundary you can investigate.

## Localize the failed boundary

Separate naming, routing, connection establishment, encryption, protocol response, and application behavior. Record source, destination, time, request type, and affected population. A successful observation at one layer does not prove the rest of the path works.

## Evaluate redundancy and change impact

Map paths and shared dependencies, including DNS, policy, gateways, links, and control systems. Define what each alternate path protects. Coordinate routing or policy changes with affected service owners and establish how you will verify the actual user path.

## Preserve regional and tenant context

Compare affected and unaffected vantage points. Aggregate success can conceal one region, resolver, tenant, or address family. Build evidence that explains the difference before changing a shared network component.

## Resources behind these responsibilities

- [Linux kernel networking documentation](https://docs.kernel.org/networking/index.html): The subsystem relevant to your observed host-network behavior. [Access and technical limits](../README.md#source-kernel-net).
- [RFC 1035: Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035): Message structure, resource records, and caching concepts. [Access and technical limits](../README.md#source-dns).
- [RFC 8446: TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446): Handshake concepts and the part relevant to your connection problem. [Access and technical limits](../README.md#source-tls).
- [Kubernetes: Debugging DNS Resolution](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/): Prerequisites and the checks matching the failing boundary. [Access and technical limits](../README.md#source-kube-dns).
- [OpenTelemetry signals](https://opentelemetry.io/docs/concepts/signals/): Signals relevant to your diagnostic question. [Access and technical limits](../README.md#source-otel).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).

[Back to Network Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Network Reliability Engineer: Production Practice Resources

Compare a failing vantage point with a healthy one before changing a shared route, resolver, or policy.

## Investigate a contrast

Compare the failing region or client with a healthy one using compatible time windows and requests. Check what differs in resolver, address, route, policy, connection state, or dependency. Avoid replacing a multi-layer investigation with a generic network restart.

## Verify changes through the affected path

After a scoped policy or routing change, observe the original source population and request. Check for unintended exposure or asymmetric effects. Preserve a timeline and distinguish mitigation from a confirmed explanation of the cause.

## A successful DNS answer leaves most of the path open

Suppose requests from region A time out while region B succeeds. Both resolve the same name, but that does not establish that they receive the same address, take the same route, or encounter the same policy.

Record the actual response, source, address family, destination, port, and time. Compare connection establishment from the failing workload with an equivalent check from the healthy one. If transport succeeds, move to TLS and application behavior rather than continuing to change DNS settings.

Use the contrast to choose the next boundary. After a policy or route change, verify the original affected request and check for unintended exposure. A successful check from your administrator session may bypass the path you needed to repair.

## Operating references

- [Linux kernel networking documentation](https://docs.kernel.org/networking/index.html): The subsystem relevant to your observed host-network behavior. [Access and technical limits](../README.md#source-kernel-net).
- [RFC 1035: Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035): Message structure, resource records, and caching concepts. [Access and technical limits](../README.md#source-dns).
- [RFC 8446: TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446): Handshake concepts and the part relevant to your connection problem. [Access and technical limits](../README.md#source-tls).
- [Kubernetes: Debugging DNS Resolution](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/): Prerequisites and the checks matching the failing boundary. [Access and technical limits](../README.md#source-kube-dns).
- [Incident Response](https://sre.google/workbook/incident-response/): Coordination, roles, communication, and follow-up. [Access and technical limits](../README.md#source-incident).
- [Google SRE Workbook: Postmortem Culture](https://sre.google/workbook/postmortem-culture/): Incident analysis, action items, and organizational learning. [Access and technical limits](../README.md#source-postmortem).

[Back to Network Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

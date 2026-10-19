# Network Reliability Engineer: Interview and Assessment Resources

Work from protocol boundaries and contrasting observations rather than treating similar timeout messages as identical failures.

## DNS resolves but connections time out

Identify what the DNS result proves and which transport, route, policy, capacity, or destination conditions remain open. Choose an observation that distinguishes alternatives from the affected vantage point.

## A failover works for some clients only

Ask about caching, connection reuse, address families, location, and routing. Explain how you would compare observations and avoid assuming that a control-plane update instantly changes every client path.

## What to look for in your answer

Use the failing vantage point and a meaningful contrast. Say what each protocol observation proves, which boundary remains open, and how the affected path is checked after a change.

## References for checking the reasoning

- [RFC 1035: Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035) · [Access and technical limits](../README.md#source-dns)
- [RFC 8446: TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446) · [Access and technical limits](../README.md#source-tls)
- [Kubernetes: Debugging DNS Resolution](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/) · [Access and technical limits](../README.md#source-kube-dns)
- [Linux kernel networking documentation](https://docs.kernel.org/networking/index.html) · [Access and technical limits](../README.md#source-kernel-net)

[Back to Network Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

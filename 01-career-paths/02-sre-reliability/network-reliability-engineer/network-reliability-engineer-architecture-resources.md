# Network Reliability Engineer: Architecture Resources

An alternate network path is useful only if clients can reach it with sufficient capacity and the required protocol behavior.

## Model the request and control paths

Show resolvers, route decisions, gateways, encryption boundaries, and policy owners. Include the systems used to change or observe the network. Loss of a shared control dependency can make otherwise independent paths difficult to operate.

## Make failover behavior concrete

Define routing convergence, resolver caches, connection reuse, capacity, and session implications. A new destination does not mean every client switches immediately. Compare objectives with the actual client behavior and the limits of the chosen mechanism.

## Design methods and implementation constraints

- [C4 model](https://c4model.com/): System context, then container diagrams when more detail is needed. [Access and technical limits](../README.md#source-c4).
- [Architecture Decision Records](https://adr.github.io/): The introductory explanation and a suitable template. [Access and technical limits](../README.md#source-adr).
- [Linux kernel networking documentation](https://docs.kernel.org/networking/index.html): The subsystem relevant to your observed host-network behavior. [Access and technical limits](../README.md#source-kernel-net).
- [RFC 1035: Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035): Message structure, resource records, and caching concepts. [Access and technical limits](../README.md#source-dns).
- [RFC 8446: TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446): Handshake concepts and the part relevant to your connection problem. [Access and technical limits](../README.md#source-tls).
- [Kubernetes: Debugging DNS Resolution](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/): Prerequisites and the checks matching the failing boundary. [Access and technical limits](../README.md#source-kube-dns).

[Back to Network Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

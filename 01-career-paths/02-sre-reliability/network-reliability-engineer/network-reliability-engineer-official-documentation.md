# Network Reliability Engineer: Official Documentation

Use the references below when you need to establish exact behavior for maintaining dependable connectivity through naming, routing, transport, policy, and failure-domain analysis. Match the installed version and actual configuration before interpreting an observation.

## What did the resolver actually establish?

Record queried name and type, response, cache context, source, and applicable implementation behavior.

Read [RFC 1035: Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035), starting with message structure, resource records, and caching concepts. Read the RFC status and updates; modern DNS behavior also depends on later specifications and resolver implementation.

## Where does TLS negotiation fail?

Distinguish transport connection, handshake stage, selected protocol, and peer context.

Read [RFC 8446: TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446), starting with handshake concepts and the part relevant to your connection problem. Certificate operations and older protocol implementations need their own matching references.

## Which cluster DNS boundary is failing?

Use the actual workload namespace, resolver configuration, DNS service, and relevant platform checks.

Read [Kubernetes: Debugging DNS Resolution](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/), starting with prerequisites and the checks matching the failing boundary. Use your cluster context deliberately; DNS answers alone do not establish application reachability.

## Related implementation references

- [Linux kernel networking documentation](https://docs.kernel.org/networking/index.html): The subsystem relevant to your observed host-network behavior. [Access and technical limits](../README.md#source-kernel-net).

[Back to Network Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

# Network Engineering

Follow the request from its source. A name resolving, a connection opening, and an application returning a useful response are different observations.

<img src="../assets/diagrams/network-request-path.svg" alt="Separate name resolution, connection, TLS when used, and application checks when investigating a request." width="100%"/>

## Learn the layer you need

**[Cloudflare: What is DNS? →](https://www.cloudflare.com/learning/dns/what-is-dns/)**  
Understand resolvers, authoritative servers, caching, and the lookup process.  
**Free · Concept guide · Beginner**

**[Wireshark User’s Guide →](https://www.wireshark.org/docs/wsug_html_chunked/)**  
Use the capture and analysis sections to learn how to inspect authorized traffic.  
**Free documentation · Intermediate · Capture permissions may be required**

**[Beej’s Guide to Network Programming →](https://beej.us/guide/bgnet/)**  
Study sockets and client/server communication through programming examples.  
**Free online · Guide · C programming familiarity needed**

## Connect the subject to your environment

| Your environment | Start here |
| --- | --- |
| Hosts, processes, and network listeners | [Linux and systems](linux-systems.md) |
| Cloud subnets, routing, and access | [Cloud platforms](cloud-engineering.md) |
| Container and cluster traffic | [Containers](https://docs.docker.com/get-started/) · [Kubernetes](kubernetes-engineering.md) |
| Failed lookups or connections | [Network troubleshooting](network-engineering.md#explain-one-connection-from-evidence) |

## Explain one connection from evidence

Use [Wireshark’s captured-packet guide](https://www.wireshark.org/docs/wsug_html_chunked/ChapterWork.html) while examining traffic between two local workloads you own. You need Wireshark and permission to capture on the selected interface; the documentation is free.

Compare a successful connection with a deliberately closed destination port. Record the source, destination, transport, and packets that support your conclusion. If you use a hostname, separate the DNS observation from the connection observation. Encrypted traffic will not reveal application contents without additional authorized decryption setup.

Keep a short annotated trace with synthetic traffic. Restore the test service, stop capture, and delete captures containing credentials or personal data.

Use [observability](observability.md) when you need to connect request behavior to service signals, or [cloud security](cloud-security.md) when access policy is the central question.

[All career paths](README.md) · [Directory homepage](../README.md)

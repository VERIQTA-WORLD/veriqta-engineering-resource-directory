# HAProxy

<a href="https://www.haproxy.org/#docs"><img src="../assets/tool-haproxy.svg" alt="HAProxy source reference" width="48" height="48"/></a>

Choose resources around the frontend, backend, and health decision you need to understand.

## Start with these

**[HAProxy configuration tutorials →](https://www.haproxy.com/documentation/haproxy-configuration-tutorials/)**  
Follow a focused proxy or health-check example.  
**Free documentation · Exercise setup and permissions vary**

[HAProxy reference](https://www.haproxy.org/#docs) · [Source and project material](https://github.com/haproxy/haproxy)

## Watch and understand

[Networking Fundamentals →](https://www.practicalnetworking.net/index/networking-fundamentals-how-data-moves-through-the-internet/)  
**Background teaching sequence · Compare older examples with the current reference**

## Longer reading

[The Site Reliability Workbook →](https://sre.google/workbook/table-of-contents/) · **Free online book**

**Operating decisions and service objectives**

## Try a small task

Balance between two synthetic backends and examine behavior when one becomes unavailable.

**Keep:** The configuration and requests showing backend selection and recovery.

**Setup:** synthetic names and dedicated test services. **Cleanup:** resolver or proxy changes, test services, and temporary certificates.

**Related discoveries:** [NGINX](nginx.md) · [Envoy](envoy.md)

[Browse this collection](README.md) · [Directory homepage](../README.md)

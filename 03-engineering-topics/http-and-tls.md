# HTTP and TLS

Separate the request, response, certificate, and connection questions when choosing a resource.

## Choose the question

| Open | What you can find | Access |
| --- | --- | --- |
| [everything curl](https://everything.curl.dev/) | Daniel Stenberg’s project book; use it to understand transfers and troubleshoot curl behavior. | Free online book |
| [Practical TLS: free first module](https://www.practicalnetworking.net/practical-tls/practical-tls-free-ssl-training-m1/) | Use the introductory lessons before investigating certificate and TLS behavior. | Free module; full course separate |
| [badssl.com](https://badssl.com/) | Inspect purpose-built TLS test cases in an authorized learning setting. | Public test endpoints; no sensitive data |
| [httpbin](https://httpbin.org/) | Use an HTTP request-and-response service for synthetic transfer experiments. | Public service; do not send credentials |
| [Web Security Academy](https://portswigger.net/web-security) | Choose a vulnerability explanation and its authorized training lab. | Free learning and labs; account for progress |

## Focused references

**[MDN HTTP guide →](https://developer.mozilla.org/en-US/docs/Web/HTTP)**  
Choose the status, header, caching, or connection subject behind a request.  
**Free reference and guides**

**[How HTTPS Works →](https://howhttps.works/)**  
Use an illustrated introduction before reading protocol details.  
**Free illustrated website**

**[TLS 1.3 specification →](https://www.rfc-editor.org/rfc/rfc8446)**  
Use the protocol reference when an exact TLS 1.3 behavior matters.  
**Free specification; advanced**

## Follow the tools

[curl](../04-tools-and-technologies/curl.md) · [Caddy](../04-tools-and-technologies/caddy.md) · [NGINX](../04-tools-and-technologies/nginx.md) · [Wireshark](../04-tools-and-technologies/wireshark.md)

## Put one idea to work

Compare a synthetic success and error response, then examine one purpose-built TLS test case. Use the selected guide’s prerequisites and verification steps. Choose an owned or provided learning environment, keep sensitive data out of your notes, and remove the exercise resources when finished.

[Browse this collection](README.md) · [Directory homepage](../README.md)

# Security Labs

Choose a deliberately vulnerable application or a clearly authorized training environment.

## Find a safe learning target

| Open | What you can find | Access |
| --- | --- | --- |
| [Web Security Academy](https://portswigger.net/web-security) | Choose a vulnerability explanation and its authorized training lab. | Free learning and labs; account for progress |
| [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/) | Use an intentionally vulnerable application as an authorized security training target. | Free source; isolated learning environment required |
| [OPA Playground](https://play.openpolicyagent.org/) | Compare policy decisions against small synthetic inputs. | Free interactive tool |
| [Kyverno Playground](https://playground.kyverno.io/) | Explore a policy against sample Kubernetes resources. | Public playground; no confidential manifests |
| [IAM policy simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) | Compare simulated decisions with the guide’s stated limitations. | Free documentation; permissions and account required |

## Make the exercise useful

Explain one finding or access decision using the request, input, policy, or code that supports it. Keep both the intended behavior and the counterexample that shows the boundary.

**Environment and cleanup:** Keep vulnerable applications isolated, use synthetic data, and remove test credentials and temporary integrations when finished.

[Browse this collection](README.md) · [Directory homepage](../README.md)

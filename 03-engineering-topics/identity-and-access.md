# Identity and Access

Separate who is acting, how they authenticate, and what they are allowed to do.

## Trace an access decision

| Open | What you can find | Access |
| --- | --- | --- |
| [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) | Study the policy context behind an allowed or denied action. | Free reference; AWS account for practice |
| [IAM policy simulator](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_testing-policies.html) | Compare simulated decisions with the guide’s stated limitations. | Free documentation; permissions and account required |
| [Security Engineering](https://www.cl.cam.ac.uk/archive/rja14/book.html) | Ross Anderson; choose a security-design chapter to understand the assumptions around a control. | Author-hosted material; edition access varies |
| [AWS Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html) | Select the workload-protection question behind a provider configuration. | Free reference; implementation can incur charges |
| [Microsoft cloud security benchmark](https://learn.microsoft.com/en-us/security/benchmark/azure/overview) | Check the benchmark version and control guidance before applying it. | Public guidance; inspect preview status |
| [Google Cloud security foundations](https://cloud.google.com/security/best-practices) | Choose a provider-specific guide for identity, data, or workload protection. | Public guide catalog |

## Follow the tools

[Active Directory](../04-tools-and-technologies/active-directory.md) · [Vault](../04-tools-and-technologies/vault.md) · [OpenBao](../04-tools-and-technologies/openbao.md)

## Put one idea to work

Write down the principal, action, resource, and context for an allowed and a denied learning request. Use the selected guide’s prerequisites and verification steps. Choose an owned or provided learning environment, keep sensitive data out of your notes, and remove the exercise resources when finished.

[Browse this collection](README.md) · [Directory homepage](../README.md)

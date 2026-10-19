# Network Reliability Engineer: Labs and Portfolio Projects

## Compare failing and healthy request paths

Investigate a synthetic connectivity mismatch from two controlled vantage points.

### Set up the exercise

Use owned local containers or VMs, a test service, synthetic names, and scoped diagnostic permissions. Document the intended path before changes.

### Investigate the behavior

Create one reversible configuration difference. Record name resolution, destination, connection behavior, encryption stage if used, and functional outcome.

Keep the contrast table, timestamps, relevant metadata, hypotheses, discriminating checks, and verified correction. Exclude private payloads.

### Finish and clean up

Restore the original network settings or remove the dedicated environment. Delete captures or logs containing unnecessary sensitive data.

### References for this project

- [Linux kernel networking documentation](https://docs.kernel.org/networking/index.html) · [Prerequisites and limitations](../README.md#source-kernel-net)
- [RFC 1035: Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035) · [Prerequisites and limitations](../README.md#source-dns)
- [RFC 8446: TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446) · [Prerequisites and limitations](../README.md#source-tls)

## Trace DNS inside a local Kubernetes cluster

Use the Kubernetes DNS guide to connect workload resolver settings with DNS service and application observations.

### Set up the exercise

Use a dedicated kind cluster, compatible tools, a synthetic workload, and the access required by the selected guide checks.

### Investigate the behavior

Compare an intentionally invalid application destination with a genuine resolver problem in the dedicated lab. Explain the different evidence.

Record names and record types, resolver context, answers or failures, application reachability, and the interpretation of each check.

### Finish and clean up

Remove dedicated test objects and the cluster. Restore any modified configuration before retaining the environment.

### References for this project

- [Kubernetes: Debugging DNS Resolution](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/) · [Prerequisites and limitations](../README.md#source-kube-dns)
- [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) · [Prerequisites and limitations](../README.md#source-kind)
- [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) · [Prerequisites and limitations](../README.md#source-debug)

[Back to Network Reliability Engineer resources](README.md) · [Browse this career collection](../README.md)

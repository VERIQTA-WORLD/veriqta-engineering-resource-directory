# DevOps Architect: Labs and Portfolio Projects

## Compare two delivery architectures

A fictional company needs a delivery path for three services with different release schedules. Compare independent repository workflows with a shared delivery service.

Produce context and execution views, a trust-boundary table, and two decision records. Choose a preferred option using operator capacity, recovery, and compatibility requirements.

### Environment and access

A design-only exercise needs a document editor and no cloud account. If you build a prototype, use only synthetic repositories and a dedicated lab environment.

### Challenge the result

Review an unavailable registry, an expired executor credential, and a data-incompatible rollback. State the evidence you need before committing to the design.

A comparison can establish reasoning quality; it does not demonstrate runtime availability.

### Cleanup

Retain the design and assumptions. Remove only prototype resources you actually created and revoke any disposable tokens.

### Implementation resources

- [C4 model](https://c4model.com/) · [Access and limitations](../README.md#source-c4)
- [Architecture Decision Records](https://adr.github.io/) · [Access and limitations](../README.md#source-adr)
- [GitHub Actions documentation](https://docs.github.com/en/actions) · [Access and limitations](../README.md#source-actions)

## Validate a local delivery boundary

Build a disposable Kubernetes learning environment and examine how Git-controlled application configuration reaches it. Use the upstream quick starts for implementation.

Record repository identity, reconciler authority, target scope, application verification, and an intentional configuration difference.

### Environment and access

You need a supported runtime, adequate local capacity, Kubernetes tools, and compatible Argo CD instructions. Git hosting or registry actions may require accounts.

### Challenge the result

In the dedicated lab, compare configuration drift with an intentionally invalid desired configuration. Explain how each appears to the controller and to the application user.

A local cluster does not reproduce production control-plane availability or cloud network behavior.

### Cleanup

Remove the application and dedicated controller or cluster using the applicable upstream instructions. Remove exercise integrations and credentials separately.

### Implementation resources

- [kind quick start](https://kind.sigs.k8s.io/docs/user/quick-start/) · [Access and limitations](../README.md#source-kind)
- [Argo CD documentation](https://argo-cd.readthedocs.io/en/stable/) · [Access and limitations](../README.md#source-argo)
- [GitHub Actions: Secure use reference](https://docs.github.com/en/actions/reference/security/secure-use) · [Access and limitations](../README.md#source-secure)

## Review recovery dependencies

Create a design review for a service whose deployment runner depends on the same environment it must recover.

Produce a dependency map, recovery access plan, data-recovery assumptions, and an acceptance checklist for a future restore test.

### Environment and access

Design-only work is suitable; use synthetic identities and architecture. Deploying a cloud test requires a dedicated account, explicit permissions, and cost controls.

### Challenge the result

Walk through runner loss, inaccessible infrastructure state, and unavailable normal identity. Identify which recovery step cannot currently be performed.

A tabletop review identifies gaps but does not measure actual recovery time.

### Cleanup

Remove any optional lab infrastructure and revoke temporary access. Record unresolved dependencies instead of inventing restore results.

### Implementation resources

- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) · [Access and limitations](../README.md#source-aws)
- [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/) · [Access and limitations](../README.md#source-sre)
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) · [Access and limitations](../README.md#source-iam)

[Back to DevOps Architect resources](README.md) · [Browse this career collection](../README.md)

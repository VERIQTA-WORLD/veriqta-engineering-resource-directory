# DevOps Engineer: Interview and Assessment Resources

Treat each prompt as an investigation: identify the missing observation before committing to a diagnosis or recovery action.

## Prompt: green pipeline, failed checkout

The rollout completes and health checks pass, but checkout fails for some users. Ask what the health checks cover, which requests fail, what changed, and whether the database dependency is compatible. Distinguish a plausible hypothesis from an established cause.

## Prompt: works locally, fails after deployment

Compare artifact identity, startup, configuration, permissions, connectivity, and dependencies. Explain how you would narrow the boundary without changing several variables at once. A container image can reduce packaging differences while leaving important environmental differences.

## Prompt: rollback does not recover

The previous image starts, but errors continue after a data change. Explain the limitations of artifact rollback and the evidence needed to choose restoration or forward repair. Identify who owns the data decision.

## What to look for in your answer

Trace the actual artifact, configuration, identity, and request. Explain why your next observation narrows the problem and why the proposed recovery is compatible with the current data state.

## References for checking the reasoning

- [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/) · [Access and technical limits](../README.md#source-debug)
- [Canarying Releases](https://sre.google/workbook/canarying-releases/) · [Access and technical limits](../README.md#source-canary)
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state) · [Access and technical limits](../README.md#source-state)
- [GitHub Actions documentation](https://docs.github.com/en/actions) · [Access and technical limits](../README.md#source-actions)
- [Incident Response](https://sre.google/workbook/incident-response/) · [Access and technical limits](../README.md#source-incident)

[Back to DevOps Engineer resources](README.md) · [Browse this career collection](../README.md)

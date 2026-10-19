# DevOps Engineer: Skills and Prerequisite Resources

When a deployment fails, your next step depends on whether you can explain startup, configuration, identity, connectivity, and persistent data.

## Understand the running application

Identify its process, startup requirements, listener, configuration, logs, and persistence needs. Learn how the service is supervised and how to observe a failed start. Container packaging changes delivery mechanics but does not remove these application dependencies.

## Understand changes and authority

Use version control to inspect differences, infrastructure state to understand resource ownership, and identity references to reason about allowed actions. Treat build access and production access as separate concerns. Know which credentials are available to each job.

## Practise diagnostic interpretation

Differentiate a name-resolution failure, connection failure, HTTP error, and application-level error. Collect evidence that separates hypotheses. A status flag can tell you where to look without explaining the user-visible problem.

## Read at the boundary you need to understand

- [Pro Git, second edition](https://git-scm.com/book/en/v2): Git Basics, then branching and the internals relevant to your question. [Access and technical limits](../README.md#source-git).
- [systemd.service reference](https://www.freedesktop.org/software/systemd/man/latest/systemd.service.html): Service type, process startup, and restart behavior. [Access and technical limits](../README.md#source-systemd).
- [Docker: Build and share a containerized application](https://docs.docker.com/get-started/tutorials/run-an-app/): Before you start, then the application workflow. [Access and technical limits](../README.md#source-docker).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html): Policy types and the linked evaluation guidance. [Access and technical limits](../README.md#source-iam).

[Back to DevOps Engineer resources](README.md) · [Browse this career collection](../README.md)

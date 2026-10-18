# DevOps Platform Engineer: Learning Resources

Learn platform engineering through a small supported workflow. Combine platform concepts, implementation references, and observation of real consumer tasks.

This page focuses on providing supported delivery capabilities that other engineers can use through predictable interfaces. **Question to keep in view:** Can a team complete a supported workflow and recover from failure without depending on undocumented platform knowledge?

## On this page

- [Start with a workflow problem](#start-with-a-workflow-problem)
- [Study metadata and authority separately](#study-metadata-and-authority-separately)
- [Learn to operate what you build](#learn-to-operate-what-you-build)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Start with a workflow problem

Choose one user group and one recurring task. Document the current path and the evidence of friction. Read platform guidance to frame the capability, then use a small prototype to test whether the proposed interface actually helps.

## Study metadata and authority separately

Learn catalog ownership and template inputs alongside authentication and permission design. This prevents an early prototype from confusing discoverability with enforcement. Use synthetic organizations, repositories, and identities for experiments.

## Learn to operate what you build

Define acceptance, support, upgrade, and retirement paths before broad adoption. Ask a second person to complete the workflow using your documentation. Their questions expose assumptions that the author of a template may not notice.

## Use a reading and practice loop

Choose one question, read the relevant section, explain it in your own words, and apply it to a small example. Record what the source established and what you still need to investigate. If the example cannot be run within your budget or authority, label the work design-only and write a validation plan.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [CNCF Platforms White Paper](https://tag-app-delivery.cncf.io/whitepapers/platforms/)

**Use it to answer:** Which supported capability helps the consumer complete a task, and who will operate it?

- **Start with:** Platform capabilities and the platform-as-product discussion.
- **Prerequisites:** Experience with developer workflows and operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-platforms) for publisher context, access conditions, and the key limitation.

### [Backstage Software Catalog](https://backstage.io/docs/features/software-catalog/)

**Use it to answer:** Which metadata describes the service and its owner, and how will stale information be detected?

- **Start with:** Entity concepts and ownership information.
- **Prerequisites:** Application-development familiarity and an appropriate Backstage environment.
- **Access and limits:** See the [maintained source annotation](../README.md#source-catalog) for publisher context, access conditions, and the key limitation.

### [Backstage Software Templates](https://backstage.io/docs/features/software-templates/)

**Use it to answer:** Which inputs become generated artifacts or external actions, and what remains after partial completion?

- **Start with:** Template structure and available actions.
- **Prerequisites:** A configured Backstage environment and integration knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-templates) for publisher context, access conditions, and the key limitation.

### [Backstage permissions overview](https://backstage.io/docs/permissions/overview/)

**Use it to answer:** Where is the permission decision enforced and which plugin or downstream action must respect it?

- **Start with:** Permission concepts and policy integration.
- **Prerequisites:** Backend development and authentication familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-permissions) for publisher context, access conditions, and the key limitation.

### [The Site Reliability Workbook](https://sre.google/workbook/table-of-contents/)

**Use it to answer:** Which reliability responsibility needs better evidence, ownership, or an operating procedure?

- **Start with:** The chapter corresponding to your current service concern.
- **Prerequisites:** Experience operating a service.
- **Access and limits:** See the [maintained source annotation](../README.md#source-sre) for publisher context, access conditions, and the key limitation.

## Apply the reading

Design a learning project around one onboarding task. Include a consumer test, a denied request, an interrupted external action, and a documented support response before adding more integrations.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Decide what to study next

If the mechanism remains unclear, open the skills and learning pages. If the uncertainty concerns supported behavior, use official documentation. If it concerns an option or boundary, use architecture resources. If the result depends on execution evidence, choose a bounded project from the labs page rather than inferring success from reading.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

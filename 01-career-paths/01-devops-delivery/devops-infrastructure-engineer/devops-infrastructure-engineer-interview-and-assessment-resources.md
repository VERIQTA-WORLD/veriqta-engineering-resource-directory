# DevOps Infrastructure Engineer: Interview and Assessment Resources

Use these original infrastructure prompts to explain state ownership, coordination, and service impact. Strong answers distinguish the tool view from the actual environment.

This page focuses on building and maintaining the compute, networking, identity, configuration, and state foundations behind software delivery. **Question to keep in view:** Can you change or rebuild infrastructure without losing control of state, access, data, and recovery?

## On this page

- [Prompt: a backend lock blocks a release](#prompt-a-backend-lock-blocks-a-release)
- [Prompt: a plan proposes replacement](#prompt-a-plan-proposes-replacement)
- [Prompt: rebuild succeeded, service failed](#prompt-rebuild-succeeded-service-failed)
- [Selected resources](#selected-resources)
- [Apply the reading](#apply-the-reading)

## Prompt: a backend lock blocks a release

A lock error occurs while another engineer may still be operating. Explain the evidence required before any unlock and how you would assess resource changes already in progress. Avoid interpreting elapsed time alone as proof of abandonment.

## Prompt: a plan proposes replacement

A provider update causes a persistent resource to be replaced. Explain how you inspect the reason, data implications, dependencies, and alternatives. Identify the conditions under which you would stop rather than apply.

## Prompt: rebuild succeeded, service failed

Infrastructure recreation completes, but the application cannot use restored data. Separate provisioning, configuration, authorization, restoration, and application compatibility. Describe evidence that narrows the failed boundary.

## Assess reasoning with evidence

Explain what you know, what remains uncertain, and which observation you need next. Compare plausible alternatives before selecting an action. Make permission, user impact, and recovery conditions explicit. Use the prompts to practise explaining your assumptions, evidence, and decisions.

## Selected resources

The order below is a task-based selection, not a requirement to complete every source. Detailed publisher, access, and limitation notes have one maintained home in the category reference directory.

### [Terraform: State locking](https://developer.hashicorp.com/terraform/language/state/locking)

**Use it to answer:** What evidence distinguishes a currently active operation from an abandoned lock?

- **Start with:** Lock behavior and force-unlock conditions.
- **Prerequisites:** Understanding of the selected backend and active operations.
- **Access and limits:** See the [maintained source annotation](../README.md#source-locking) for publisher context, access conditions, and the key limitation.

### [Terraform: State](https://developer.hashicorp.com/terraform/language/state)

**Use it to answer:** Which resources does the tool track, and how does that mapping relate to actual infrastructure?

- **Start with:** The purpose of state and its relationship to resources.
- **Prerequisites:** Basic Terraform configuration and provider knowledge.
- **Access and limits:** See the [maintained source annotation](../README.md#source-state) for publisher context, access conditions, and the key limitation.

### [Terraform: Tests](https://developer.hashicorp.com/terraform/language/tests)

**Use it to answer:** Does this test inspect a plan, execute changes, or substitute mocked behavior, and what can it prove?

- **Start with:** Test files, run blocks, and assertions.
- **Prerequisites:** Compatible Terraform version and provider prerequisites.
- **Access and limits:** See the [maintained source annotation](../README.md#source-tests) for publisher context, access conditions, and the key limitation.

### [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

**Use it to answer:** Which policy layers determine whether the execution identity can perform the requested action?

- **Start with:** Policy types and the linked evaluation guidance.
- **Prerequisites:** AWS identities, resources, and basic JSON familiarity.
- **Access and limits:** See the [maintained source annotation](../README.md#source-iam) for publisher context, access conditions, and the key limitation.

### [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

**Use it to answer:** Which workload assumption needs review across reliability, security, operations, performance, cost, or sustainability?

- **Start with:** The framework overview and the pillar relevant to your review.
- **Prerequisites:** A defined workload and stakeholder requirements.
- **Access and limits:** See the [maintained source annotation](../README.md#source-aws) for publisher context, access conditions, and the key limitation.

## Apply the reading

Respond with a change timeline, ownership map, and verification plan. Include what needs workload-owner approval and which observation would change your next action.

### Evidence to keep

Record the question, environment or design assumptions, selected reference sections, your observations, and the reasoning behind the result. Label simulated examples and design-only work. Keep uncertainty separate from verified behavior, and remove private data from any evidence you publish.

### Review your answer

| Dimension | A useful answer shows | A gap to investigate |
| --- | --- | --- |
| Scope | A clear affected system and constraints | A product choice before requirements |
| Evidence | Observations that separate explanations | A guessed cause presented as fact |
| Trade-offs | Alternatives and consequences | One unconditional best practice |
| Authority | Appropriate ownership and access | Unreviewed changes to shared systems |
| Recovery | Verification and persistent side effects | A retry or rollback with no conditions |

Attempt the reasoning before consulting the sources. If another person reviews your answer, ask which unsupported assumption most affects the recommendation.

[Role resource directory](README.md) · [DevOps delivery collection](../README.md) · [All career paths](../../README.md)

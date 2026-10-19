# DevOps Infrastructure Engineer: Learning Resources

Study a small resource lifecycle before adding shared state and recovery complexity. Keep configuration management and application data visible as separate responsibilities.

## Learn lifecycle behavior locally

A local Docker-based infrastructure tutorial can introduce configuration, state, and teardown without requiring a cloud account. Inspect the state relationship and external runtime behavior. Do not infer cloud permissions, resilience, or networking from the local example.

## Add configuration and drift

Use a separate disposable host when studying configuration management. Change a known setting manually and examine how the tool reports or corrects it. Explain why repeated execution changes or preserves the result based on the actual tasks.

## Study recovery as separate work

Record which files and services are needed to reconstruct the environment. Consider loss of local configuration, inaccessible state, and unavailable execution credentials separately. Infrastructure rebuild and data restoration require different evidence.

## A focused reading list

- [Terraform Docker tutorial collection](https://developer.hashicorp.com/terraform/tutorials/docker-get-started): Prerequisites, infrastructure lifecycle, and destroy instructions. [Access and technical limits](../README.md#source-tf-lab).
- [Terraform: State](https://developer.hashicorp.com/terraform/language/state): The purpose of state and its relationship to resources. [Access and technical limits](../README.md#source-state).
- [Ansible playbooks](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_intro.html): Playbook execution and desired-state task structure. [Access and technical limits](../README.md#source-ansible).
- [Ansible check and diff modes](https://docs.ansible.com/projects/ansible/latest/playbook_guide/playbooks_checkmode.html): Module support and the limitations of check mode. [Access and technical limits](../README.md#source-check).
- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html): The framework overview and the pillar relevant to your review. [Access and technical limits](../README.md#source-aws).

## Your next study decision

Complete a learning plan with configuration, state inspection, controlled change, drift investigation, and teardown. Record what the local exercise cannot establish about a cloud deployment.

[Back to DevOps Infrastructure Engineer resources](README.md) · [Browse this career collection](../README.md)

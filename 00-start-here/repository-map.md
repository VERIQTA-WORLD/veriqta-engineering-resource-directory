# Repository map

This map explains the directory's architecture and where different questions belong. Use it to find a starting point, understand a linked destination, or place a contribution in the correct section.

The structure is broader than a single course. It includes public learning and reference material alongside the systems needed to catalogue, review, and maintain that material. Many sections are still under development; the descriptions below explain their intended responsibilities.

## Main sections

| Section | Purpose | Typical question |
| --- | --- | --- |
| [00 Start Here](README.md) | Orientation and browsing routes | Where should I begin? |
| [01 Career paths](../01-career-paths/) | Roles, responsibilities, progression, and learning resources | What work does this role involve? |
| [02 Tools](../02-tools/) | Technologies organized by engineering capability | Which tool fits this task? |
| [03 Technical domains](../03-technical-domains/) | Foundations and disciplines behind engineering work | How does this system or concept work? |
| [04 Cloud providers](../04-cloud-providers/) | Provider-specific material and cloud operating contexts | How does this apply in this environment? |
| [05 Technology ecosystems](../05-technology-ecosystems/) | Projects, extensions, integrations, and connected components | How do these technologies fit together? |
| [06 Production problems](../06-production-problems/) | Symptoms, evidence, investigation, mitigation, and recovery | How should I investigate this failure? |
| [07 Documentation](../07-documentation/) | Routes to authoritative product and technical documentation | Where is the relevant reference? |
| [08 Learning resources](../08-learning-resources/) | Evaluated learning material and its intended use | Which resource suits my level and goal? |
| [09 Standards and RFCs](../09-standards-and-rfcs/) | Specifications and formal technical guidance | What requirements or interfaces apply? |
| [10 Reference architectures](../10-reference-architectures/) | Designs, assumptions, boundaries, and tradeoffs | How might these components form a system? |
| [11 Postmortems](../11-postmortems/) | Incident accounts and engineering lessons | What can we learn from a failure? |
| [12 Indexes](../12-indexes/) | Lookup views across the collection | Where else is this subject referenced? |
| [13 Resource catalogue](../13-resource-catalog/) | Canonical records, aliases, and relationships | Which record represents this resource? |
| [14 Templates](../14-templates/) | Structures and instructions for authoring material | What must this content type contain? |
| [15 Quality assurance](../15-quality-assurance/) | Review criteria, verification, and audit records | What supports this resource's readiness? |
| [16 Contributor guides](../16-contributor-guides/) | Detailed contribution procedures | How should I add or update this material? |
| [17 Automation scripts](../17-automation-scripts/) | Validation and index-building implementations | Which checks can be performed automatically? |
| [18 Site and search](../18-site-and-search/) | Site configuration, navigation, and search | How is the directory presented and searched? |
| [19 Maintenance](../19-maintenance/) | Coverage, stale content, priorities, and releases | What needs updating next? |

RFC means Request for Comments. The standards section will distinguish formal specifications from drafts and historical documents; the label alone does not tell you a document's current status.

## Understand the main distinctions

### Career versus domain

A career is organized around responsibilities. A domain is organized around knowledge. A platform engineer may need networking, delivery, security, and observability knowledge, while each of those domains is useful to several careers.

Use careers to decide what work you want to understand. Use domains to develop the knowledge needed for that work.

### Tool versus ecosystem

A tool is a particular implementation or utility. An ecosystem explains how connected projects and extensions support a wider purpose. A tool page should help you assess the implementation; an ecosystem page should help you understand responsibilities and integration boundaries.

Neither a tool list nor an ecosystem diagram means that every component is required for your environment.

### Cloud provider versus technical domain

Cloud material gives an environment-specific view. Networking and identity concepts still matter across providers, but their service names, configuration, limits, and operational responsibilities can differ. Understand the concept, then examine the selected context.

Some cloud folders describe platforms or operating models rather than vendors. The [cloud browsing guide](browse-by-cloud.md) explains this classification.

### Problem guide versus postmortem

A problem guide helps you investigate a class of symptoms in your own context. A postmortem describes a particular incident and the evidence reported about it. Lessons from a postmortem can inform an investigation, but they do not establish the cause of a new failure.

### Index versus catalogue

An index is a browsing view. The catalogue is intended to hold the canonical information that those views reference. One resource may appear in several indexes without becoming several independent resources. See [resource identifiers](understand-resource-ids.md) for the intended identity model and current implementation limits.

## What to expect inside subject folders

Career folders have separate files for curriculum, production responsibilities, toolkit, learning resources, official documentation, and related careers. Domain folders separate curriculum, documentation, standards, tools, production problems, and related domains.

Cloud folders organize major operational concerns into topic files. Ecosystems separate core projects, integrations, extensions, learning, security, and production context. Production problem folders separate symptoms, triage, diagnostic decisions, commands, mitigation, verification, prevention, and references.

These file boundaries keep explanations focused. Read the folder README before choosing a deeper file, and follow the recommended sequence when it exists.

## Root and asset files

The [root README](../README.md) introduces the collection. Root standards and policies are intended to define editorial expectations, resource conventions, identifier rules, contribution procedures, and link verification. Other root files cover licensing, notices, security, support, roadmap, citation, and change history.

The `assets` directory contains banners, diagrams, icons, logos, and asset guidance. Visual assets support navigation and teaching; they are not evidence that software, a site, or an exercise has been implemented.

## Current development boundaries

Directory paths can exist while their files remain empty. This map is a guide to the architecture, not a publication checklist. Assess content readiness at the destination. In particular, catalogue conventions, validation scripts, contributor policies, and site configuration must not be assumed operational merely because their files are present.

To learn how to move through the map, continue with [How to use this repository](how-to-use-this-repository.md). To report a gap or propose a focused addition, read the [contribution guide](contribution-guide.md).

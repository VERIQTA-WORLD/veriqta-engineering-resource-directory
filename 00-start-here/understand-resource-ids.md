# Understand resource IDs

A resource identifier gives a catalogue record a stable identity. It lets several parts of the directory refer to the same resource without creating conflicting copies of its information.

This guide explains the intended identity model for readers and contributors. It does not define a final identifier syntax. The repository's ID naming policy, registry, and catalogue schema are currently placeholders, so there is no populated convention to apply from those files yet.

## Why names and paths are not enough

A resource can be relevant to several careers, domains, ecosystems, or problems. Its title may change, an external URL may move, or a file may be reorganized. Without a stable identity, those references can become disconnected or duplicated.

An identifier allows the catalogue to retain the same record while updating descriptive or location information. This is a proposed design responsibility, not a claim that the current repository already implements every part of that behavior.

## Distinguish identity from location and classification

| Concept | What it represents | Example of a change |
| --- | --- | --- |
| Identifier | The identity of a catalogue record | Normally retained when a record is renamed |
| Title | A human-readable name | Wording changes for clarity |
| Path or URL | Where the resource can be found | A file moves or a documentation URL changes |
| Alias | Another name or reference associated with the identity | A former title is recorded for lookup |
| Category or topic | How the resource is grouped | An additional relevant domain is attached |
| Relationship | How one record relates to another | A tool is linked to a domain it supports |
| Lifecycle status | Whether a resource is active, archived, or otherwise classified under adopted rules | A superseded resource is retained as historical material |

A category is not an identifier. A lifecycle label is not evidence that a command was tested. Keep identity, classification, publication state, and verification evidence distinct.

## One record can have several useful views

**Illustrative example:** a diagnostic tool is relevant to a networking domain, a career toolkit, and a production investigation. Those pages should reference the same canonical resource information when the catalogue is implemented.

Each page can explain its local relevance. The networking page may explain the protocol concept; the toolkit may explain the responsibility; the incident guide may explain which observation the tool supports. They should not create competing records with different claims about the same resource.

## What counts as a distinct resource?

A shared title does not prove two entries are identical. Two documents might cover different versions, audiences, or scopes. Conversely, two URLs might redirect to the same document.

Before merging or creating records, compare the resource type, publisher, canonical location, version scope, and intended use. The adopted catalogue policy must determine whether versions are separate records or attributes of one record. Do not make that decision differently in every folder.

When uncertain, preserve the evidence and report a possible duplicate rather than deleting information or assigning new identities immediately.

## Relationships should explain something

A relationship is useful when it tells the reader how resources connect. Examples of relationship meanings include a tool supporting a domain, documentation describing a project, a prerequisite supporting a learning path, or an architecture using a component.

These are explanatory examples, not final machine-readable relationship names. The schema must define accepted relationship types, direction, required fields, and validity rules before catalogue data is populated at scale.

Avoid vague associations that add links without helping a reader understand what to do with them.

## Preserve identity through changes

Once conventions are adopted, a title change should not automatically create a new identity. Location changes should update the canonical destination and affected references. An alias or redirect can preserve discoverability when appropriate.

Retirement should retain useful history and explain why a resource is no longer recommended. Do not silently reuse a retired identifier for a different resource. Review any merge or replacement according to the adopted policy so that related references remain coherent.

These are recommended identity principles to implement in the authoritative policy. They must not be represented as already enforced by working automation.

## Current contributor boundary

Until the naming policy and schema are established:

1. Identify the resource by its exact path or URL and descriptive title in a proposal.
2. Check nearby files for an existing record or reference.
3. Record possible duplicates, aliases, and relationships for review.
4. Do not invent an ID format, fabricate registry entries, or claim schema validation.
5. Keep content changes separate from unresolved catalogue decisions.

Public reading and useful authoring can continue while catalogue conventions are being developed. The absence of a final identifier format does not justify describing a placeholder as a validated record.

## Authoritative locations

The [ID naming policy](../ID-NAMING-CONVENTION.md) is intended to define syntax and assignment. The [ID registry](../12-indexes/id-registry.csv) is intended to track assigned identities. The [resource catalogue](../13-resource-catalog/) contains the intended schema, canonical records, aliases, and relationships. The [indexes](../12-indexes/) provide lookup views.

Consult those files when they are populated and adopted. If they conflict, report the inconsistency rather than choosing a new convention locally.

Continue with the [contribution guide](contribution-guide.md), review the [repository map](repository-map.md), or return to [Start Here](README.md).

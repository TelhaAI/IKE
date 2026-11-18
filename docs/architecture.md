# Architecture (starting point)

This is a first sketch to build on, not a final design.

```
Studio UI (apps/studio)
   |  proposals, reviews, approvals
   v
Agent service (services/agents)
   |  REST / gRPC / MCP
   v
IKE engine (databridge_AI, ike/)

All three share one ontology format: packages/ontology-schema
```

## Pieces

**Studio UI.** A canvas and editor for an ontology: concepts, relationships, properties and constraints. Shows each agent proposal as a reviewable change with its evidence. The user accepts, edits or rejects.

**Agent service.** Hosts the design agents. A first cut of roles:
- *Modeler* drafts concepts and relationships from a domain description or sample data.
- *Reviewer* checks a draft for gaps, duplicates and conflicts with what IKE already knows.
- *Curator* turns approved changes into versioned ontology releases and publishes them to IKE.

**Ontology schema.** One JSON Schema for the ontology document, so the UI, the agents and IKE agree on the format. A starting draft is in `packages/ontology-schema/ontology.schema.json`.

## Open decisions
- UI stack for `apps/studio`.
- Agent runtime (Claude Agent SDK, MCP tools against IKE, or both).
- Where ontology versions are stored: in IKE's Postgres store or in this repo's service.
- How ontologies relate to IKE's existing persona packs and knowledge types.

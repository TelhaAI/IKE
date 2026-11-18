# IKE Design Studio

IKE (Institutional Knowledge Engine) Design Studio is a workspace where AI agents help people design, review and manage ontologies for IKE.

A user describes a domain, and agents propose concepts, relationships and constraints, check them against existing knowledge, and explain each suggestion. The user accepts, edits or rejects each change, and the approved ontology is published to IKE.

> Status: initial scaffold. Nothing here runs yet.

## Layout

| Path | What lives there |
|------|------------------|
| `apps/studio/` | The Design Studio user interface (web app). Stack not chosen yet. |
| `services/agents/` | Python service that hosts the ontology design agents and talks to IKE. |
| `packages/ontology-schema/` | The shared ontology format (JSON Schema) used by the UI, the agents and IKE. |
| `docs/` | Architecture notes and design decisions. |

## Relationship to DataBridge AI

The IKE engine itself lives in [`TelhaAI/databridge_AI`](https://github.com/TelhaAI/databridge_AI) under `ike/`. It exposes REST, gRPC and MCP APIs plus a Python client (`ike.client`). This repo builds on those APIs. It does not copy IKE code.

See [`docs/architecture.md`](docs/architecture.md) for the starting design.

## License

Apache 2.0, see [`LICENSE`](LICENSE).

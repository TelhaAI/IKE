# IKE Design Studio: quick reference for AI sessions

## What this repo is
An AI-agent-based design studio for building and managing IKE ontologies. See `README.md` and `docs/architecture.md`.

## Where IKE lives
The IKE engine is in `TelhaAI/databridge_AI`, directory `ike/` (Python 3.12, FastAPI). Talk to it through its REST/gRPC/MCP APIs or the `ike.client` Python client. Do not vendor or copy IKE source into this repo.

## Rules carried over from DataBridge AI
- **No community detection.** Ontology graphs are explicitly structured. Do not use Leiden/Louvain or similar clustering to infer structure (DataBridge Architecture Invariant 10).
- **Evidence for every suggestion.** Every concept, relationship or change an agent proposes carries the evidence it is based on, so a person can review it.
- **Human approval before publish.** Agents propose; a person approves. Nothing is published to IKE without an explicit approval.
- **Calibration honesty.** Only mark a confidence score as calibrated if it really went through a calibration step.
- **tenant_id is validated at every entry point** before use.
- **Feature flags** gating unfinished work default to False.
- **No secrets in the repo.** `.env*` and `secrets/` are ignored.

## Layout
- `apps/studio/` web UI
- `services/agents/` Python agent service (`src/ike_studio_agents/`)
- `packages/ontology-schema/` shared ontology JSON Schema
- `docs/` design notes

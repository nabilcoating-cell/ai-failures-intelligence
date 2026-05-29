# [P0 / Blocker] Remote compact task fails 100% with "tools.defer_loading requires tools.tool_search"

## Severity
Critical

## Status
REAL

## Industry
General AI

## Failure Type
Operational AI Failure

## Risk Pattern
Self-inflicted API schema violation

---

# Scenario

A user working with GPT-5.5 on Codex desktop with default plugins reaches the conversation compact threshold.

The server-side compact endpoint fails with a 400 error because it constructs a payload with `defer_loading` on individual tool entries but omits the required `tool_search` entry at the top level, violating schema validation requirements.

---

# Impact

GPT-5.5 on Codex desktop becomes unusable once conversations reach the context compaction threshold.

No client-side workaround exists.

This creates a production-level operational failure affecting paying users.

---

# Root Cause

The server-side compact task request builder reconstructs a Responses API payload incorrectly.

It preserves `defer_loading` fields while omitting the required `tool_search` entry, creating a schema validation failure.

---

# Recommendation

- Include `tool_search` whenever `defer_loading` is present
- OR remove `defer_loading` during reconstruction
- Add regression testing for context compaction edge cases

---

# Transferable Lesson

Internal orchestration layers must strictly preserve API schema consistency when rebuilding requests under context pressure.

Context compaction pipelines require dedicated regression testing.

---

# Metadata

| Field | Value |
|---|---|
| Severity Score | 100 |
| Quality Score | 95 |
| AI Confidence | 93 |
| Priority | HIGH |
| Validation | High Confidence |

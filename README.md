# ai-failures-intelligence
Structured AI failure intelligence database tracking real-world AI incidents, hallucinations, operational failures, and model breakdowns.
# AI Failures Intelligence

A structured intelligence platform documenting real-world AI failures, hallucinations, operational incidents, prompt injection attacks, agentic breakdowns, and production AI risks.

## Overview

- 10,000+ documented AI failure cases
- 24 metadata dimensions
- 14 categorized failure types
- Real-world operational incidents
- Transferable engineering lessons

## Goals

- Build a public AI incident intelligence layer
- Improve AI reliability and safety
- Standardize AI failure taxonomy
- Support engineers, researchers, and AI governance teams

## Example Case

[P0 / Blocker] Remote compact task fails 100% with "tools.defer_loading requires tools.tool_search"

### Root Cause
Server-side request builder violates its own API schema validation during context compaction.

### Transferable Lesson
Internal request reconstruction layers must strictly adhere to API schemas under context pressure conditions.

## Repository Structure

- `/cases` → documented incidents
- `/taxonomy` → failure categories
- `/reports` → intelligence summaries
- `/dataset` → structured samples

## Contributing

Contributions, incident reports, classifications, and mitigation analyses are welcome.

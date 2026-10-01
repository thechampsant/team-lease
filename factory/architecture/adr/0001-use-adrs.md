# ADR 0001 — Record architecture decisions

Status: accepted
Date: <YYYY-MM-DD>

## Context

Agents need to know not just what was decided but what was rejected and why.
Without the rejected alternatives, a later agent re-proposes a discarded option
with total confidence, because nothing in the repo says otherwise.

## Decision

Every architectural decision is recorded as a numbered ADR in this directory,
before implementation. The architect role writes it; the human approves it.

## Alternatives rejected

- Decisions captured in chat history — disappears between sessions.
- Decisions captured in a wiki — drifts from the code and nobody updates it.

## Consequences

- Architecture changes cost one file and one approval.
- Agents can be pointed at a directory rather than a person.

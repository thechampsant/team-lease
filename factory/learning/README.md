# Learning log (human-owned)

Append-only JSONL in `log.jsonl`. Agents must not rewrite this directory.

Each close of an escalation or reviewer reject is one line:

```json
{"ts":"2026-09-15T00:00:00Z","task":"T-014","kind":"escalation","root_cause":"wrong files","note":"tests/ui owned by T-008"}
```

`root_cause` is one of: `unclear order`, `missing tests`, `wrong files`, `unsafe action`, `bad review`, `tool problem`.

**Monthly:** promote recurring tags into `CURRENT.md` (and into product / techlead role methods if the pattern is stable). Recurring CR categories go into `patterns.md`. `./bin/factory` concatenates `CURRENT.md`, `patterns.md`, plus the last learning lines into every agent prompt.

Cold third-model audits live in `factory/runs/audit/AUDIT-NNN.md` (`kind: audit` in the log). Check-ins live in `factory/intake/checkins/`.

Do not invent USD. Do not delete lines.

# Approvals

Evidence that gate G0 passed lives here. Downstream `factory run` roles
refuse until a matching file exists. Never delete anything from this folder.

`./bin/factory approve <gate> --file PATH` copies a `.txt` or `.pdf` here as
`<gate>-<UTC-date>.<ext>` (your git identity, not `factory-agent`). After a
**product** approval it stubs `factory/tasks/T-NNN.yaml` for **architect** if
none exists; after **architect**, a **techlead** stub. It does not create qa
or developer tasks. Optional `--run` (no args) starts that stub; `--run ROLE
TASK` still starts an explicit pair. Never deletes this folder.

Pre-seed: a `.txt` paste of the client's "approved" email is enough. Signed
PDFs are fine when you have them.

| Gate | Filename prefix | Unlocks |
|---|---|---|
| product | `prd-*` or `product-*` | `architect` |
| architect | `architecture-*` or `architect-*` | techlead, qa, developer, reviewer, designer, sre, writer |
| release | `release-*` | nothing in the CLI (record only; you still deploy) |

`product` may run with an empty folder. Every other role must appear in a
gate's `unlocks` list in `factory/config.yaml` and have matching evidence.

A file matches when its basename starts with `<prefix>-`. `README.md` does
not count.

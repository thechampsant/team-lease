# Acceptance criteria

Every criterion has a stable ID. Tasks reference these IDs, tests reference
these IDs, and the reviewer checks the diff against them. Never renumber.

Format is strict so it can be parsed by the gate. An example (inside a code
block, so the gate ignores it):

```
## AC-01 — Short title

**Given** some starting state
**When** some action occurs
**Then** some observable outcome

**Verified by:** `tests/path/to/test_file.py::test_ac_1_name`
```

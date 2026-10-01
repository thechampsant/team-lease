# Design

Visual specification for in-scope UI. Empty until a **designer** task runs.

Designer owns this directory. UI implementers read it and do not invent
tokens or layout that contradict it. Backend-only slices leave it unused.

What the Designer writes here:

- a text spec per screen: layout, hierarchy, the four states, and which API
  field each control shows;
- `tokens.css`: colours, type, spacing and radii as CSS variables, light and
  dark;
- `mockups/<screen>--<state>.html`: one static page per screen and state,
  using `../tokens.css`. No scripts and nothing from the internet: Factory
  Studio shows them in a locked-down frame on the job's **Design** tab.

A person reacts with `factory feedback <job> --text "..."` (or **Change
something** in Studio); the Designer reads it on its next try
(`factory run designer <job>`).

